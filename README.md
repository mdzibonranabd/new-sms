# new-sms
sms
class Result extends StatelessWidget{
  final int resultScore;
  final VoidCallback resetHandler;

  Result(this.resultScore, this.resetHandler);

  String get resultPharse{
    String resultText;
    if(resultScore>40){
      resultText= "Tumi Porimoni";
    } else if(resultScore>30){
      resultText= "Tumi Opu Biswas";
    }else if(resultScore>20){
      resultText= "Tumi Bubli";
    } else if(resultScore>10){
      resultText= "Tumi Popy";
    } else{
      resultText="Tumi Mithila";
    }
    return resultText;
  }




  @override
  Widget build(BuildContext context) {
    return Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: <Widget>[
          Text(
            resultPharse,
            style: TextStyle(fontSize: 26,fontWeight: FontWeight.bold),
            textAlign: TextAlign.center,
          ),
          Text(
            'Score: ' '$resultScore',
            style: TextStyle(fontSize: 30,fontWeight: FontWeight.bold),
            textAlign: TextAlign.center,
          ),
          FlatButton(
            child: Text('Reset Quiz'),
            textColor: Colors.blueAccent,
            onPressed:resetHandler,
          )
        ],
      ),
    );
  }
}

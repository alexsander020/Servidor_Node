var express = require("express");
var app = express();
var bodyParser = require("body-parser");
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true }));
var post = process.env.POST || 3000;

app.get("/", function (req, res) {
  res.send("Teobando");
});

app.get("/teste", function (req, res) {
  res.send("Astoufo");
});

app.post("/cadastro", function (req, res) {
  console.log(req.body);
  console.log("Recebi um dados: ");

  let nome = req.body.nome;
  let senha = req.body.senha;

  console.log(`Nome: ${nome} Senha: ${senha}`);

  res.send("Dados recebidos");
});

app.listen(post);

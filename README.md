export default function QuemTaCerto() {
  const [nome1, setNome1] = useState("");
  const [versao1, setVersao1] = useState("");
  const [nome2, setNome2] = useState("");
  const [versao2, setVersao2] = useState("");
  const [vencedor, setVencedor] = useState("");

  function decidir() {
    if (!nome1 || !nome2 || !versao1 || !versao2) {
      alert("Preencha tudo, amorzinhos!");
      return;
    }

    const quemGanhou = Math.random() < 0.5 ? nome1 : nome2;
    setVencedor(quemGanhou);
  }

  return (
    <div className="min-h-screen bg-pink-100 flex flex-col items-center justify-center p-6 text-center">
      <h1 className="text-3xl font-bold text-pink-700 mb-6">💔 Quem Tá Certo?</h1>
      
      <div className="grid grid-cols-1 md:grid-cols-2 gap-6 w-full max-w-4xl">
        <div className="bg-white p-4 rounded-2xl shadow-md">
          <input
            className="w-full p-2 rounded mb-2 border"
            placeholder="Nome 1"
            value={nome1}
            onChange={(e) => setNome1(e.target.value)}
          />
          <textarea
            className="w-full p-2 rounded border"
            placeholder="Sua versão dos fatos"
            rows={4}
            value={versao1}
            onChange={(e) => setVersao1(e.target.value)}
          />
        </div>

        <div className="bg-white p-4 rounded-2xl shadow-md">
          <input
            className="w-full p-2 rounded mb-2 border"
            placeholder="Nome 2"
            value={nome2}
            onChange={(e) => setNome2(e.target.value)}
          />
          <textarea
            className="w-full p-2 rounded border"
            placeholder="Sua versão dos fatos"
            rows={4}
            value={versao2}
            onChange={(e) => setVersao2(e.target.value)}
          />
        </div>
      </div>

      <button
        onClick={decidir}
        className="mt-6 bg-pink-600 text-white px-6 py-2 rounded-xl shadow hover:bg-pink-700 transition"
      >
        Decidir quem tá certo
      </button>

      {vencedor && (
        <div className="mt-6

import React, { useState } from "react";

const robots = [
  {
    name: "Ziko",
    img: "https://i.imgur.com/TWq5Pi0.png",
    story: "Ziko é o líder da revolução ZIKA, sempre estrategista e otimista.",
    speech: "Vamos dominar o blockchain juntos!"
  },
  {
    name: "Nova",
    img: "https://i.imgur.com/pAq0mHL.png",
    story: "Nova é a especialista em segurança, protegendo suas transações.",
    speech: "Segurança em primeiro lugar!"
  },
  {
    name: "Byte",
    img: "https://i.imgur.com/M7RZPcR.png",
    story: "Byte é o programador mestre, garantindo que tudo funcione bem.",
    speech: "Código limpo, swaps rápidos!"
  }
];

export default function App() {
  const [fromAmount, setFromAmount] = useState("");
  const [toAmount, setToAmount] = useState("");
  const tokenSymbol = "$ZIKA";

  const handleSwap = () => {
    alert("Swap executado (simulado)");
  };

  return (
    <div style={{
      minHeight: "100vh",
      background: "linear-gradient(to right, #0f0c29, #302b63, #24243e)",
      color: "white",
      fontFamily: "'Orbitron', sans-serif",
      padding: "2rem"
    }}>
      {/* Banner Etherzica */}
      <div style={{ textAlign: "center", marginBottom: "2rem" }}>
        <img
          src="https://i.imgur.com/z7kNd8P.png" // <- Substitua por outro link se quiser
          alt="Banner Etherzica"
          style={{
            maxWidth: "100%",
            borderRadius: "1rem",
            boxShadow: "0 0 15px rgba(0,0,0,0.5)"
          }}
        />
      </div>

      {/* Robôs com fala */}
      <div style={{ textAlign: "center", marginBottom: "3rem" }}>
        <h1 style={{ fontSize: "2.5rem", fontWeight: "bold" }}>
          Bem-vindo ao Futuro da Troca Cripto
        </h1>
        <p style={{ fontSize: "1rem", marginTop: "0.5rem" }}>
          Conheça o universo dos robôs ZIKA: uma revolução no blockchain
        </p>

        <div style={{ display: "flex", justifyContent: "center", gap: "2rem", marginTop: "2rem", flexWrap: "wrap" }}>
          {robots.map((robot, i) => (
            <div key={i} style={{ width: "150px", position: "relative" }}>
              <img
                src={robot.img}
                alt={robot.name}
                style={{ width: "100%", animation: `float ${3 + i * 0.5}s ease-in-out infinite` }}
              />
              <div style={{
                position: "absolute",
                top: "-70px",
                left: "50%",
                transform: "translateX(-50%)",
                backgroundColor: "#3b82f6",
                padding: "0.75rem 1rem",
                borderRadius: "1rem",
                color: "white",
                fontSize: "0.9rem",
                boxShadow: "0 2px 10px rgba(0,0,0,0.3)",
                zIndex: 10,
                animation: `fadeIn 3s ease-in-out infinite alternate`
              }}>
                {robot.speech}
              </div>
              <div style={{ marginTop: "0.75rem", fontWeight: "bold", fontSize: "1rem" }}>
                {robot.name}
              </div>
              <div style={{ fontSize: "0.8rem", marginTop: "0.3rem", color: "#cbd5e1" }}>
                {robot.story}
              </div>
            </div>
          ))}
        </div>
      </div>

      {/* Gráfico do Bitcoin */}
      <div style={{ maxWidth: "1000px", margin: "0 auto 3rem", background: "#1e293b", padding: "1rem", borderRadius: "1rem" }}>
        <h2 style={{ textAlign: "center", fontSize: "1.5rem", marginBottom: "1rem" }}>
          Gráfico do Bitcoin (BTC) em Tempo Real
        </h2>
        <iframe
          src="https://s.tradingview.com/widgetembed/?frameElementId=tradingview_d2493&symbol=BINANCE:BTCUSDT&interval=1&theme=dark&style=1&timezone=America%2FSao_Paulo"
          width="100%"
          height="400"
          style={{ border: "none", borderRadius: "1rem" }}
          allowFullScreen
        ></iframe>
      </div>

      {/* Swap */}
      <div style={{
        maxWidth: "420px",
        margin: "0 auto",
        padding: "2rem",
        background: "rgba(255,255,255,0.05)",
        borderRadius: "1rem",
        boxShadow: "0 8px 25px rgba(0,0,0,0.3)"
      }}>
        <h2 style={{ textAlign: "center", fontSize: "1.5rem", marginBottom: "1rem" }}>
          Swap SOL ⇄ {tokenSymbol}
        </h2>

        <label>De (SOL)</label>
        <input
          type="number"
          value={fromAmount}
          onChange={(e) => setFromAmount(e.target.value)}
          placeholder="Digite o valor em SOL"
          style={{
            width: "100%",
            padding: "0.5rem",
            margin: "0.5rem 0 1rem 0",
            borderRadius: "0.5rem",
            border: "none",
            color: "black"
          }}
        />

        <label>Para ({tokenSymbol})</label>
        <input
          type="number"
          value={toAmount}
          onChange={(e) => setToAmount(e.target.value)}
          placeholder={`Valor estimado em ${tokenSymbol}`}
          style={{
            width: "100%",
            padding: "0.5rem",
            marginBottom: "1rem",
            borderRadius: "0.5rem",
            border: "none",
            color: "black"
          }}
          disabled
        />

        <div style={{ marginBottom: "1rem", color: "#facc15" }}>
          Taxa de 2% será aplicada
        </div>

        <button
          onClick={handleSwap}
          style={{
            width: "100%",
            padding: "0.75rem",
            backgroundColor: "#3b82f6",
            border: "none",
            borderRadius: "0.75rem",
            color: "white",
            fontWeight: "bold",
            cursor: "pointer"
          }}
        >
          Confirmar Swap
        </button>

        <div style={{ marginTop: "1rem", textAlign: "center" }}>
          Conectar carteira (em breve)
        </div>
      </div>

      {/* Animações CSS */}
      <style>
        {`
          @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
          }
          @keyframes fadeIn {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
          }
        `}
      </style>
    </div>
  );
}

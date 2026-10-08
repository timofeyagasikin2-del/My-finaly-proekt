from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
    # Данные для отображения (можно позже заменить на API или БД)
    facts = [
        {"title": "Рост температуры", "text": "Средняя температура Земли с доиндустриального периода выросла примерно на 1.2 °C."},
        {"title": "CO₂ в атмосфере", "text": "Концентрация CO₂ превысила 420 ppm — это максимум за сотни тысяч лет."},
        {"title": "Таяние ледников", "text": "Ледники теряют массу, из‑за чего растёт уровень моря."},
        {"title": "Экстремальные явления", "text": "Волны жары, засухи и ливни становятся чаще и сильнее."}
    ]

    sources = ["IPCC", "NOAA", "NASA"]

    return render_template("index.html", facts=facts, sources=sources)

if __name__ == "__main__":
    app.run(debug=True)

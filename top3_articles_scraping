from bs4 import BeautifulSoup
import requests

responde = requests.get("https://news.ycombinator.com/news")
yc_web_page = responde.text

soup = BeautifulSoup(yc_web_page, "html.parser")
materias= soup.findAll(name="a", class_="titlelink")
lista_links = []
lista_name = []

for materia in materias:
    materia_name = materia.get_text()
    lista_name.append(materia_name)
    materia_link = materia.get("href")
    lista_links.append(materia_link)

scores = [int(score.getText().split()[0]) for score in soup.findAll(name="span", class_="score")]

maior_pont = max(scores)
maior_index = scores.index(maior_pont)

top3 = sorted(range(len(scores)), key=lambda i: scores[i], reverse=True)

for each in range(0,3):
    print(lista_name[each])
    print(lista_links[each])
    print(maior_pont)

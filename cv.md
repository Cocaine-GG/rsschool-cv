# Daniiel KONDRATIUK

![Profile image](https://dk67-portfolio.web.app/myPhoto.c1a656d1.jfif)
****

## Contacts

* +33 7 52 37 38 09
* [d.kondratiuk67@gmail.com](mailto:d.kondratiuk67@gmail.com?subject=[GitHub]%20RSS%20School)
* [Linkedin](https://www.linkedin.com/in/daniel-kondratiuk-5b51551a2/)
* [Telegram](https://t.me/cocaine_gg)
* [My Portfolio](https://dk67-portfolio.web.app/)

****

## About

**I see the goal, but I see no obstacles**

* Autonomy
* Perseverance
* Adaptability
* Curiosity

****

## Skills

* JavaScript / ReactJS / NodeJS
* PHP /Laravel / Symfony
* HTML/CSS
* SQL

****

## Example Code:

#### [Telegram Bot](https://github.com/Cocaine-GG/telegram-bot-coin-galaxy)

``` javascript
async function actionHandler(ctx){
	console.log(ctx.from)
	let firstValue, secondValue
	if (ctx.update.callback_query !== undefined) {
		[firstValue, secondValue] = ctx.update.callback_query.data.split(' ')
	}
	if (ctx.message !== undefined) {
		[firstValue, secondValue] = ctx.message.text.split(' ')
	}

	const findUser = USERS.find(el=>el.id===ctx.from.id)
	if(!findUser){
		USERS.push(ctx.from)
		savedUsers(USERS)
	}

	const url = process.env.API_URL + firstValue + '_' + secondValue
	if (firstValue && secondValue) {
		try {
			const {data} = await axios.get(url)
			const [bidsPrice, bidsCount] = data.bids[0]
			const [asksPrice, asksCount] = data.asks[0]

			return ctx.replyWithMarkdown(`Вы можете купить ${firstValue.toUpperCase()}
Цена за 1 ${firstValue.toUpperCase()} = *${bidsPrice} ${secondValue.toUpperCase()}*
По текущей цене доступно *${bidsCount} ${firstValue.toUpperCase()}*

Вы можете продать ${firstValue.toUpperCase()}
За 1 ${firstValue.toUpperCase()} вы получите *${asksPrice} ${secondValue.toUpperCase()}*
По текущей цене можно продать *${asksCount} ${firstValue.toUpperCase()}*
`)
		} catch (err) {
			return ctx.replyWithMarkdown(`Данной валютной *${firstValue} ${secondValue}*  не существует
Попробуйте изменить порядок
Например *${secondValue} ${firstValue}*`)
		}
	}
	return ctx.replyWithMarkdown(`Введите коректно пару валют
Например *WEC USD*`)
}
```

****

## Education

* Front-end developer (september 2021) [OpenClassRooms](https://openclassrooms.com/)
* Web Developer (fev 2020 - may 2020) [WebForce 3](https://www.wf3.fr/)

****

## Work Experience

* 6 months internship at [My Client Is Rich](https://www.myclientisrich.com/)

****

## Language

* English: **Elementary / Pre-Intermediate**
* French: **Intermediate**

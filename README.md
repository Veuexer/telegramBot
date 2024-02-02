
import telebot
import random
from telebot import types


bot = telebot.TeleBot('-')

EngToRus_Countries_nationalities_languages_Adjectives_referring_to_people_countries_languages = ['british', 'irish', 'flemish', 'polish', 'danish', 'turkish', 'spanish', 'canadian', 'brazilian', 'latvian', 'korean', 'russian',  'australian', 'japanese', 'chinese', 'vietnamese', 'portuguese', 'maltese', 'taiwanese', 'israeli', 'iraqi', 'kuwaiti', 'pakistani',   'yemeni', 'bangladeshi', 'icelandic', 'arabic', 'slavonic']
EngToRus_Countries_nationalities_languages_Nationalities = [  'finn', 'swede', 'turk', 'spaniard', 'dane', 'briton', 'arab', 'pole', 'german', 'italian', 'belgian', 'catalan', 'greek', 'african', 'european']
EngToRus_Countries_nationalities_languages_World_regions = [   'north america', 'the arctic', 'scandinavia', 'europe', 'the mediterranean', 'north africa', 'the atlantic', 'the far east',  'antarctica', 'the pacic', 'australia', 'the antarctic', 'asia', 'east asia', 'the middle east', 'the indian ocean', 'central america', 'south america', 'the caribbean', 'southern africa']
EngToRus_Weather_Cold = ['icicle', 'snowstorm', 'snowdrift', 'black ice', 'snowbroth', 'cool', 'chilly', 'nippy ', 'cold', 'brisk', 'raw', 'freezing cold', 'biting', 'below zero', 'arctic', 'cold snap', 'to snow', 'to sleet', 'to hail', 'snowflake', 'frozen rain', 'hailstones', 'ear muffs', 'scarf', 'mittens', 'woolly jumper', 'down—padded coat']
EngToRus_Weather_Warm = ['stifling', 'muggy', 'boiling hot', 'heatwave', 'sunny', 'hot', 'scorching heat', 'warm', 'sunny', 'cloudless']
EngToRus_Weather_Wet_weather = ['shower', 'heavy rain', 'to pour down', 'torrential rain', 'flood', 'downpour', 'drizzle', 'thunderstorm', 'lightning', 'whirlwind', 'puddle', 'mud', 'rainbow']
EngToRus_Weather_Wind = ['wind', 'breeze', 'typhoon', 'cyclone', 'hurricane', 'storm', 'gale-force', 'fierce', 'blustery', 'brisk', 'howling', 'icy', 'gusty', 'favourable', 'biting']
EngToRus_Weather_Clouds_and_fog = ['fog', 'mist', 'haze', 'cloudy', 'nebulosity', 'overcast']
EngToRus_Weather_Climat =  ['climat', 'climat type', 'equatorial', 'subequatorial', 'tropical', 'subtropical', 'temperate', 'subpolar', 'subarctic', 'polar']
EngToRus_Weather_Weather_forecast = ['weather forecast', 'weather forecaster', 'weatherman', 'to give the weather forecast', 'the forecast is for', 'cyclon in spreading west', 'a change in the weather']

RusToEng_Countries_nationalities_languages_Adjectives_referring_to_people_countries_languages = [ 'великобританский', 'ирландский', 'фламандский', 'польский', 'датский', 'турецкий', 'испанский', 'канадский', 'бразильский', 'латышский', 'корейский', 'русский', 'австралийский', 'японский', 'китайский', 'вьетнамский', 'португальский', 'мальтийский','тайваньский', 'израильский', 'иракский', 'кувейтский', 'пакистанский', 'йеменский', 'бангладешский', 'исландский', 'арабский', 'славянский']
RusToEng_Countries_nationalities_languages_Nationalities = [  'финн', 'швед', 'турок', 'испанец', 'датчанин', 'британец', 'араб', 'поляк', 'немец', 'итальянец', 'бельгиец', 'каталонец', 'грек', 'африканец', 'европеец']
RusToEng_Countries_nationalities_languages_World_regions = ['северная америка', 'арктика', 'скандинавия', 'европа', 'средиземное море', 'северная африка', 'атлантика', 'дальний восток' , 'антарктида', 'тихий океан', 'австралия', 'антарктика', 'азия', 'восточная азия', 'ближний восток', 'индийский океан',  'центральная америка', 'южная америка', 'карибы', 'южная африка']
RusToEng_Weather_Cold = ['сосулька', 'вьюга', 'сугроб', 'наледь', 'растаявший снег', 'прохладно', 'морозно', 'зябко', 'холодно', 'холодновато с порывами ветра', 'сыро и холодно', 'леденящий холод', 'морозно', 'ниже нуля', 'холоднее некуда', 'резкое похолодание', 'идет снег', 'идет мокрый снег', 'идет град', 'снежинка', 'снег с дождем', 'градины', 'меховые ушки', 'шарф', 'варежки', 'шерстяной джемпер', 'куртка-пуховик']
RusToEng_Weather_Warm = ['удушающий', 'влажный', 'очень жарко', 'период сильной жары', 'солнечно', 'жарко', 'пекло', 'тепло', 'солнечно', 'безоблачно']
RusToEng_Weather_Wet_weather = ['ливень', 'проливной дождь', 'хлынуть', 'ливневый дождь', 'наводнение', 'дождь', 'мелкий дождь', 'гроза', 'молния', 'буря', 'лужа', 'слякоть', 'радуга']
RusToEng_Weather_Wind = ['ветер', 'легкий ветер', 'тайфун', 'циклон', 'ураган', 'шторм', 'шквальный', 'свирепый', 'бушующий', 'свежий', 'завывающий', 'ледяной', 'порывистый', 'попутный', 'пронзительный']
RusToEng_Weather_Clouds_and_fog =  ['туман', 'дымка', 'легкая дымка', 'облачно', 'облачность', 'пасмурно']
RusToEng_Weather_Climat = ['климат', 'тип климата', 'экваториальный', 'субэкваториальный', 'тропический', 'субтропический', 'умеренный', 'субполярный', 'субантарктический', 'полярный']
RusToEng_Weather_Weather_forecast = ['прогноз погоды', 'синоптик', 'метеоролог', 'передавать прогноз погоды', 'прогноз обещает', 'циклон двигается на запад', 'изменение погоды']

last_words = {
    }


last_chosen = {

}
Dictionary = {
    'EngToRus' : {
        'Countries_nationalities_languages' : {
            'Adjectives_referring_to_people_countries_languages': {
                'british': 'великобританский',
                'irish': 'ирландский',
                'polish': 'польский',
                'turkish': 'турецкий',
                'danish': 'датский',
                'spanish': 'испанский',
                'canadian': 'канадский',
                'brazilian': 'бразильский',
                'latvian': 'латышский',
                'korean': 'корейский',
                'russian': 'русский',
                'australian': 'австралийский',
                'japanese': 'японский',
                'chinese': 'китайский',
                'vietnamese': 'вьетнамский',
                'portuguese': 'португальский',
                'maltese': 'мальтийский',
                'taiwanese': 'тайваньский',
                'israeli': 'израильский',
                'iraqi': 'иракский',
                'kuwaiti': 'кувейтский',
                'pakistani': 'пакистанский',
                'yemeni': 'йеменский',
                'bangladeshi': 'бангладешский',
                'icelandic': 'исландский',
                'arabic': 'арабский',
                'slavonic': 'славянский',
                'swiss': 'швейцарский',
                'thai': 'тайский',
                'greek': 'греческий',
                'dutch': 'голландский',
                'cypriot': 'кипрский',
                'flemish': 'фламандский'
                },
            'Nationalities': {
                'finn': 'финн',
                'swede': 'швед',
                'turk': 'турок',
                'spaniard': 'испанец',
                'dane': 'датчанин',
                'briton': 'британец',
                'arab': 'араб',
                'pole': 'поляк',
                'german': 'немец',
                'italian': 'итальянец',
                'belgian': 'бельгиец',
                'catalan': 'каталонец',
                'greek': 'грек',
                'african': 'африканец',
                'european': 'европеец'
                },
            'World regions' : {
                'north america': 'северная америка',
                'the arctic': 'арктика',
                'scandinavia': 'скандинавия',
                'europe': 'европа',
                'the mediterranean': 'средиземное море',
                'north africa': 'северная африка',
                'the atlantic': 'атлантика',
                'the far east': 'дальний восток',
                'antarctica': 'антарктида',
                'the pacic': 'тихий океан',
                'australia': 'австралия',
                'the antarctic': 'антарктика',
                'asia': 'азия',
                'east asia': 'восточная азия',
                'the middle east': 'ближний восток',
                'the indian ocean': 'индийский океан',
                'central america': 'центральная америка',
                'south america': 'южная америка',
                'the caribbean': 'карибы',
                'southern africa': 'южная африка'
                }           
            },
         'Weather' : {
            'Cold' : {
                'icicle' : 'сосулька',
                'snowstorm' : 'вьюга',
                'snowdrift' : 'сугроб',
                'black ice' : 'наледь',
                'snowbroth' : 'растаявший снег',
                'cool' : 'прохладно',
                'chilly' : 'морозно',
                'nippy ' : 'зябко',
                'cold' : 'холодно',
                'brisk' : 'холодновато с порывами ветра',
                'raw' : 'сыро и холодно',
                'freezing cold' : 'леденящий холод',
                'biting' : 'морозно',
                'below zero' : 'ниже нуля',
                'arctic' : 'холоднее некуда',
                'cold snap' : 'резкое похолодание',
                'to snow' : 'идет снег',
                'to sleet' : 'идет мокрый снег',
                'to hail' : 'идет град',
                'snowflake' : 'снежинка',
                'frozen rain' : 'снег с дождем',
                'hailstones' : 'градины',
                'ear muffs' : 'меховые ушки',
                'scarf' : 'шарф',
                'mittens' : 'варежки',
                'woolly jumper' : 'шерстяной джемпер',
                'down—padded coat' : 'куртка-пуховик'
                },
            'Warm':{
                'stifling' : 'удушающий',
                'muggy' : 'влажный',
                'boiling hot' : 'очень жарко',
                'heatwave' : 'период сильной жары',
                'sunny' : 'солнечно',
                'hot' : 'жарко',
                'scorching heat' : 'пекло',
                'warm' : 'тепло',
                'sunny' : 'солнечно',
                'cloudless' : 'безоблачно',
                },
            'Wet weather':{
                'shower' : 'ливень',
                'heavy rain' : 'проливной дождь',
                'to pour down' : 'хлынуть',
                'torrential rain' : 'ливневый дождь',
                'flood' : 'наводнение',
                'downpour' : 'дождь',
                'drizzle' : 'мелкий дождь',
                'thunderstorm' : 'гроза',
                'lightning' : 'молния',
                'whirlwind' : 'буря',
                'puddle' : 'лужа',
                'mud' : 'слякоть',
                'rainbow' : 'радуга',
                },
            'Wind' : {
                'wind' : 'ветер',
                'breeze' : 'легкий ветер',
                'typhoon' : 'тайфун',
                'cyclone' : 'циклон',
                'hurricane' : 'ураган',
                'storm' : 'шторм',
                'gale-force' : 'шквальный',
                'fierce' : 'свирепый',
                'blustery' : 'бушующий',
                'brisk' : 'свежий',
                'howling' : 'завывающий',
                'icy' : 'ледяной',
                'gusty' : 'порывистый',
                'favourable' : 'попутный',
                'biting' : 'пронзительный',
                },
            'Clouds and fog' : {
                'fog' : 'туман',
                'mist' : 'дымка',
                'haze' : 'легкая дымка',
                'cloudy' : 'облачно',
                'nebulosity' : 'облачность',
                'overcast' : 'пасмурно',
                },
            'Climat' : {
                'climat' : 'климат',
                'climat type' : 'тип климата',
                'equatorial' : 'экваториальный',
                'subequatorial' : 'субэкваториальный',
                'tropical' : 'тропический',
                'subtropical' : 'субтропический',
                'temperate' : 'умеренный',
                'subpolar' : 'субполярный',
                'subarctic' : 'субантарктический',
                'polar' : 'полярный'
                },
            'Weather forecast' : {
                'weather forecast' : 'прогноз погоды',
                'weather forecaster' : 'синоптик',
                'weatherman' : 'метеоролог',
                'to give the weather forecast' : 'передавать прогноз погоды',
                'the forecast is for' : 'прогноз обещает',
                'cyclon in spreading west' : 'циклон двигается на запад',
                'a change in the weather' : 'изменение погоды',
                }
            },
        },
        

    'RusToEng' : {
        'Countries_nationalities_languages' : {
            'Adjectives_referring_to_people_countries_languages': {
                'великобританский': 'british',
                'ирландский': 'irish',
                'польский': 'polish',
                'турецкий': 'turkish',
                'датский': 'danish',
                'испанский': 'spanish',
                'канадский': 'canadian',
                'бразильский': 'brazilian',
                'латышский': 'latvian',
                'корейский': 'korean',
                'русский': 'russian',
                'австралийский': 'australian',
                'японский': 'japanese',
                'китайский': 'chinese',
                'вьетнамский': 'vietnamese',
                'португальский': 'portuguese',
                'мальтийский': 'maltese',
                'тайваньский': 'taiwanese',
                'израильский': 'israeli',
                'иракский': 'iraqi',
                'кувейтский': 'kuwaiti',
                'пакистанский': 'pakistani',
                'йеменский': 'yemeni',
                'бангладешский': 'bangladeshi',
                'исландский': 'icelandic',
                'арабский': 'arabic',
                'славянский': 'slavonic',
                'швейцарский': 'swiss',
                'тайский': 'thai',
                'греческий': 'greek',
                'голландский': 'dutch',
                'кипрский': 'cypriot',
                'фламандский' : 'flemish'
                },
            'Nationalities': {
                'финн': 'finn',
                'швед': 'swede',
                'турок': 'turk',
                'испанец': 'spaniard',
                'датчанин': 'dane',
                'британец': 'briton',
                'араб': 'arab',
                'поляк': 'pole',
                'немец': 'german',
                'итальянец': 'italian',
                'бельгиец': 'belgian',
                'каталонец': 'catalan',
                'грек': 'greek',
                'африканец': 'african',
                'европеец': 'european'
                },
            'World regions' : {
                'северная америка': 'north america',
                'арктика': 'the arctic',
                'скандинавия': 'scandinavia',
                'европа': 'europe',
                'средиземное море': 'the mediterranean',
                'северная африка': 'north africa',
                'атлантика': 'the atlantic',
                'дальний восток': 'the far east',
                'антарктида': 'antarctica',
                'тихий океан': 'the pacic',
                'австралия': 'australia',
                'антарктика': 'the antarctic',
                'азия': 'asia',
                'восточная азия': 'east asia',
                'ближний восток': 'the middle east',
                'индийский океан': 'the indian ocean',
                'центральная америка': 'central america',
                'южная америка': 'south america',
                'карибы': 'the caribbean',
                'южная африка': 'southern africa'
                }           
            },
        'Weather' : {
            'Cold' : {
                'сосулька' : 'icicle',
                'вьюга' : 'snowstorm',
                'сугроб' : 'snowdrift',
                'наледь' : 'black ice',
                'растаявший снег' : 'snowbroth',
                'прохладно' : 'cool',
                'морозно' : 'chilly',
                'зябко' : 'nippy ',
                'холодно' : 'cold',
                'холодновато с порывами ветра' : 'brisk',
                'сыро и холодно' : 'raw',
                'леденящий холод' : 'freezing cold',
                'морозно' : 'biting',
                'ниже нуля' : 'below zero',
                'холоднее некуда' : 'arctic',
                'резкое похолодание' : 'cold snap',
                'идет снег' : 'to snow',
                'идет мокрый снег' : 'to sleet',
                'идет град' : 'to hail',
                'снежинка' : 'snowflake',
                'снег с дождем' : 'frozen rain',
                'градины' : 'hailstones',
                'меховые ушки' : 'ear muffs',
                'шарф' : 'scarf',
                'варежки' : 'mittens',
                'шерстяной джемпер' : 'woolly jumper',
                'куртка-пуховик' : 'down—padded coat'
                },
            'Warm':{
                'удушающий' : 'stifling',
                'влажный' : 'muggy',
                'очень жарко' : 'boiling hot',
                'период сильной жары' : 'heatwave',
                'солнечно' : 'sunny',
                'жарко' : 'hot',
                'пекло' : 'scorching heat',
                'тепло' : 'warm',
                'солнечно' : 'sunny',
                'безоблачно' : 'cloudless'
                },
            'Wet weather':{
                'ливень' : 'shower',
                'проливной дождь' : 'heavy rain',
                'хлынуть' : 'to pour down',
                'ливневый дождь' : 'torrential rain',
                'наводнение' : 'flood',
                'дождь' : 'downpour',
                'мелкий дождь' : 'drizzle',
                'гроза' : 'thunderstorm',
                'молния' : 'lightning',
                'буря' : 'whirlwind',
                'лужа' : 'puddle',
                'слякоть' : 'mud',
                'радуга' : 'rainbow'
                },
            'Wind' : {
                'ветер' : 'wind',
                'легкий ветер' : 'breeze',
                'тайфун' : 'typhoon',
                'циклон' : 'cyclone',
                'ураган' : 'hurricane',
                'шторм' : 'storm',
                'шквальный' : 'gale-force',
                'свирепый' : 'fierce',
                'бушующий' : 'blustery',
                'свежий' : 'brisk',
                'завывающий' : 'howling',
                'ледяной' : 'icy',
                'порывистый' : 'gusty',
                'попутный' : 'favourable',
                'пронзительный' : 'biting'
                },
            'Clouds and fog' : {
                'туман' : 'fog',
                'дымка' : 'mist',
                'легкая дымка' : 'haze',
                'облачно' : 'cloudy',
                'облачность' : 'nebulosity',
                'пасмурно' : 'overcast'
                },
            'Climat' : {
                'климат' : 'climat',
                'тип климата' : 'climat type',
                'экваториальный' : 'equatorial',
                'субэкваториальный' : 'subequatorial',
                'тропический' : 'tropical',
                'субтропический' : 'subtropical',
                'умеренный' : 'temperate',
                'субполярный' : 'subpolar',
                'субантарктический' : 'subarctic',
                'полярный' : 'polar'
                },
            'Weather forecast' : {
                'прогноз погоды' : 'weather forecast',
                'синоптик' : 'weather forecaster',
                'метеоролог' : 'weatherman',
                'передавать прогноз погоды' : 'to give the weather forecast',
                'прогноз обещает' : 'the forecast is for',
                'циклон двигается на запад' : 'cyclon in spreading west',
                'изменение погоды' : 'a change in the weather'
                }
            }
        }
   }

@bot.message_handler(commands=['start'])
def start(message):
    markup = types.InlineKeyboardMarkup()
    button_1 = types.InlineKeyboardButton('Yes', callback_data='start_practise')
    button_2 = types.InlineKeyboardButton('No', callback_data='exit')
    markup.row(button_1, button_2)
    bot.reply_to(message, 'Would you like to check some words?', reply_markup=markup)
    
@bot.message_handler(commands=['change_mode'])
def change_mode(message):
    markup = types.InlineKeyboardMarkup()   
    button_1 = types.InlineKeyboardButton('English -> Russian', callback_data='EngToRus')
    button_2 = types.InlineKeyboardButton('Russian -> English', callback_data='RusToEng')
    markup.row(button_1, button_2)
    bot.send_message(message.chat.id, "Choose mode, please", reply_markup=markup)

@bot.message_handler(commands=['exit'])
def exit(message):
    bot.send_message(message.chat.id, 'Have a good day')

@bot.message_handler()
def get_word(message):
    if last_chosen.get(message.chat.id, False) != False:
        if (last_chosen[message.chat.id] == 'RusToEng_W_Cold'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_Cold'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Cold'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_W_Warm'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_Warm'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Warm'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_W_Wet'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_Wet'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Wet weather'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_W_Wind'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_Wind'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Wind'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_W_CaF'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_CaF'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Clouds and fog'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_W_Climat'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_Climat'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Climat'][last_words[message.chat.id]]
            bot.delete_message(message.chat.id, message.message_id - 1)
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_W_WF'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_W_WF'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_W'))
            right_word = Dictionary['RusToEng']['Weather']['Weather forecast'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)


        if (last_chosen[message.chat.id] == 'EngToRus_W_Cold'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_Cold'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Cold'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_W_Warm'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_Warm'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Warm'][last_words[message.chat.id]]
            bot.delete_message(message.chat.id, message.message_id - 1)
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_W_Wet'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_Wet'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Wet weather'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_W_Wind'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_Wind'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Wind'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_W_CaF'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_CaF'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Clouds and fog'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_W_Climat'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_Climat'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Climat'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_W_WF'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_W_WF'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_W'))
            right_word = Dictionary['EngToRus']['Weather']['Weather forecast'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)


        if (last_chosen[message.chat.id] == 'RusToEng_CNL_Adj'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_CNL_Adj'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_CNL'))
            right_word = Dictionary['RusToEng']['Countries_nationalities_languages']['Adjectives_referring_to_people_countries_languages'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_CNL_N'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_CNL_N'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_CNL'))
            right_word = Dictionary['RusToEng']['Countries_nationalities_languages']['Nationalities'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'RusToEng_CNL_WR'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='RusToEng_CNL_WR'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='RusToEng_CNL'))
            right_word = Dictionary['RusToEng']['Countries_nationalities_languages']['World regions'][last_words[message.chat.id]]
            bot.delete_message(message.chat.id, message.message_id - 1)
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_CNL_Adj'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_CNL_Adj'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_CNL'))
            right_word = Dictionary['EngToRus']['Countries_nationalities_languages']['Adjectives_referring_to_people_countries_languages'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_CNL_N'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_CNL_N'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_CNL'))
            right_word = Dictionary['EngToRus']['Countries_nationalities_languages']['Nationalities'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        if (last_chosen[message.chat.id] == 'EngToRus_CNL_WR'):
            markup = types.InlineKeyboardMarkup()
            markup.add(types.InlineKeyboardButton('Yes', callback_data='EngToRus_CNL_WR'))
            markup.add(types.InlineKeyboardButton('Change subtopic', callback_data='EngToRus_CNL'))
            right_word = Dictionary['EngToRus']['Countries_nationalities_languages']['World regions'][last_words[message.chat.id]]
            if message.text.lower() == right_word:
                bot.send_message(message.chat.id, 'You are correct!\nContinue?', reply_markup=markup)
            else:
                bot.send_message(message.chat.id, f"You are not correct\!\nRight answer is ||**{right_word}**|| \nContinue?", parse_mode='MarkdownV2', reply_markup=markup)
        last_chosen[message.chat.id] = 'None'

@bot.callback_query_handler(func=lambda callback: True)
def callback_message(callback):
    if callback.data == 'start_practise':
         markup = types.InlineKeyboardMarkup()
         button_1 = types.InlineKeyboardButton('English -> Russian', callback_data= 'EngToRus')
         button_2 = types.InlineKeyboardButton('Russian -> English', callback_data= 'RusToEng')
         markup.add(button_1, button_2) 
         bot.delete_message(callback.message.chat.id, callback.message.message_id)
         bot.send_message(callback.message.chat.id, 'Choose mode, please', reply_markup=markup)
         

    if callback.data == 'exit':
         bot.send_message(callback.message.chat.id, 'Ok')

    #
                                                                        #ПЕРЕВОД С РУССКОГО НА АНГЛИЙСКИЙ
    #

    if callback.data == 'RusToEng':
        markup = types.InlineKeyboardMarkup()
        markup.add(types.InlineKeyboardButton('Countries, Nationalities and Languages', callback_data='RusToEng_CNL'))
        markup.add(types.InlineKeyboardButton('Weather', callback_data='RusToEng_W')) 
        markup.add(types.InlineKeyboardButton('Change language', callback_data='start_practise') )
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, 'What would you like to check?', reply_markup=markup)
        


    if callback.data == 'RusToEng_CNL':
        markup = types.InlineKeyboardMarkup()
        markup.add(types.InlineKeyboardButton('Adjectives', callback_data='RusToEng_CNL_Adj')) 
        markup.add(types.InlineKeyboardButton('Nationalities', callback_data='RusToEng_CNL_N'))
        markup.add(types.InlineKeyboardButton('World regions', callback_data='RusToEng_CNL_WR')) 
        markup.add(types.InlineKeyboardButton('Change theme', callback_data='RusToEng')) 
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, 'What topic would you like to choose?', reply_markup=markup)

    if callback.data == 'RusToEng_W':
        markup = types.InlineKeyboardMarkup()
        markup.add(types.InlineKeyboardButton('Cold weather', callback_data='RusToEng_W_Cold')) 
        markup.add(types.InlineKeyboardButton('Warm weather', callback_data='RusToEng_W_Warm'))
        markup.add(types.InlineKeyboardButton('Wet weather', callback_data='RusToEng_W_Wet')) 
        markup.add(types.InlineKeyboardButton('Wind', callback_data='RusToEng_W_Wind')) 
        markup.add(types.InlineKeyboardButton('Clouds and fog', callback_data='RusToEng_W_CaF')) 
        markup.add(types.InlineKeyboardButton('Climat', callback_data='RusToEng_W_Climat')) 
        markup.add(types.InlineKeyboardButton('Weather forecast', callback_data='RusToEng_W_WF'))
        markup.add(types.InlineKeyboardButton('Change theme', callback_data='RusToEng')) 
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, 'What topic would you like to choose?', reply_markup=markup)

        #ПОГОДА С РУССКОГО НА АНГЛИЙСКИЙ

    if callback.data == 'RusToEng_W_Cold':
        word = random.choice(RusToEng_Weather_Cold)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_Cold'

    if callback.data == 'RusToEng_W_Warm':
        word = random.choice(RusToEng_Weather_Warm)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_Warm'

    if callback.data == 'RusToEng_W_Wet':
        word = random.choice(RusToEng_Weather_Wet_weather)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_Wet'

    if callback.data == 'RusToEng_W_Wind':
        word = random.choice(RusToEng_Weather_Wind)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_Wind'

    if callback.data == 'RusToEng_W_CaF':
        word = random.choice(RusToEng_Weather_Clouds_and_fog)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_CaF'

    if callback.data == 'RusToEng_W_Climat':
        word = random.choice(RusToEng_Weather_Climat)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_Climat'

    if callback.data == 'RusToEng_W_WF':
        word = random.choice(RusToEng_Weather_Weather_forecast)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_W_WF'


        #СТРАНЫ ЯЗЫКИ НАЦИОНАЛЬНОСТИ НА АНГЛИЙСКИЙ 

    if callback.data == 'RusToEng_CNL_Adj':
        word = random.choice(RusToEng_Countries_nationalities_languages_Adjectives_referring_to_people_countries_languages)
        last_words[callback.message.chat.id] = word
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_CNL_Adj'
        

    if callback.data == 'RusToEng_CNL_N':
        word = random.choice(RusToEng_Countries_nationalities_languages_Nationalities)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'RusToEng_CNL_N'
        

    if callback.data == 'RusToEng_CNL_WR':
        word = random.choice(RusToEng_Countries_nationalities_languages_World_regions)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        last_words[callback.message.chat.id] = word
        bot.send_message(callback.message.chat.id, word)
        last_chosen[callback.message.chat.id] = 'RusToEng_CNL_WR'
    

    #   
                                                                        #ПЕРЕВОД С АНГЛИЙСКОГО НА РУССКИЙ
    #


    if callback.data == 'EngToRus':
        markup = types.InlineKeyboardMarkup()
        markup.add(types.InlineKeyboardButton('Countries, Nationalities and Languages', callback_data='EngToRus_CNL'))
        markup.add(types.InlineKeyboardButton('Weather', callback_data='EngToRus_W')) 
        markup.add(types.InlineKeyboardButton('Change language', callback_data='start_practise'))# EngToRus: Countries nationalities languages
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, 'What would you like to check?', reply_markup=markup)


    if callback.data == 'EngToRus_CNL':
        markup = types.InlineKeyboardMarkup()
        markup.add(types.InlineKeyboardButton('Adjectives', callback_data='EngToRus_CNL_Adj')) # EngToRus: Countries nationalities languages: Adjectives
        markup.add(types.InlineKeyboardButton('Nationalities', callback_data='EngToRus_CNL_N')) # EngToRus: Countries nationalities languages: Nationalities
        markup.add(types.InlineKeyboardButton('World regions', callback_data='EngToRus_CNL_WR'))
        markup.add(types.InlineKeyboardButton('Change theme', callback_data='EngToRus'))# EngToRus: Countries nationalities languages: World regions
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, 'What topic would you like to choose?', reply_markup=markup)

    if callback.data == 'EngToRus_W':
        markup = types.InlineKeyboardMarkup()
        markup.add(types.InlineKeyboardButton('Cold weather', callback_data='EngToRus_W_Cold')) 
        markup.add(types.InlineKeyboardButton('Warm weather', callback_data='EngToRus_W_Warm'))
        markup.add(types.InlineKeyboardButton('Wet weather', callback_data='EngToRus_W_Wet')) 
        markup.add(types.InlineKeyboardButton('Wind', callback_data='EngToRus_W_Wind')) 
        markup.add(types.InlineKeyboardButton('Clouds and fog', callback_data='EngToRus_W_CaF')) 
        markup.add(types.InlineKeyboardButton('Climat', callback_data='EngToRus_W_Climat')) 
        markup.add(types.InlineKeyboardButton('Weather forecast', callback_data='EngToRus_W_WF'))
        markup.add(types.InlineKeyboardButton('Change theme', callback_data='EngToRus')) 
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, 'What topic would you like to choose?', reply_markup=markup)

        #ПОГОДА НА РУССКИЙ

    if callback.data == 'EngToRus_W_Cold':
        word = random.choice(EngToRus_Weather_Cold)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_Cold'

    if callback.data == 'EngToRus_W_Warm':
        word = random.choice(EngToRus_Weather_Warm)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_Warm'

    if callback.data == 'EngToRus_W_Wet':
        word = random.choice(EngToRus_Weather_Wet_weather)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_Wet'

    if callback.data == 'EngToRus_W_Wind':
        word = random.choice(EngToRus_Weather_Wind)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_Wind'

    if callback.data == 'EngToRus_W_CaF':
        word = random.choice(EngToRus_Weather_Clouds_and_fog)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_CaF'

    if callback.data == 'EngToRus_W_Climat':
        word = random.choice(EngToRus_Weather_Climat)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_Climat'

    if callback.data == 'EngToRus_W_WF':
        word = random.choice(EngToRus_Weather_Weather_forecast)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_W_WF'


        #СТРАНЫ НАЦИОНАЛЬНОСТИ ЯЗЫКИ НА РУССКИЙ

    if callback.data == 'EngToRus_CNL_Adj':
        word = random.choice(EngToRus_Countries_nationalities_languages_Adjectives_referring_to_people_countries_languages)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_CNL_Adj'


    if callback.data == 'EngToRus_CNL_N':
        word = random.choice(EngToRus_Countries_nationalities_languages_Nationalities)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_CNL_N'


    if callback.data == 'EngToRus_CNL_WR':
        word = random.choice(EngToRus_Countries_nationalities_languages_World_regions)
        bot.delete_message(callback.message.chat.id, callback.message.message_id)
        bot.send_message(callback.message.chat.id, word)
        last_words[callback.message.chat.id] = word
        last_chosen[callback.message.chat.id] = 'EngToRus_CNL_WR'
        

bot.polling(none_stop=True)


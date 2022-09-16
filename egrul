# -*- coding: utf8 -*-
"""
Description: Мультипоточный парсер данных ЕГРЮЛ с сайта налоговой.
Autor: Иргит Валерий
GitHub:
"""
import requests
import time
import os
import uuid
import random
import argparse


def get_requests(url, header=None, proxy=None, cookies=None):
    headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:83.0) Gecko/20100101 Firefox/83.0'}
    s = requests.Session()
    s.headers.update(headers)
    if header:
        s.headers.update(header)
    if proxy:
        s.proxies.update(proxy)
    if cookies:
        s.cookies.update(cookies)
    r = s.get(url)
    if r.status_code == 200:
        return r.text
    else:
        print('Сервер недоступен')
        return None


def get_proxy(random_proxy=False):
    """ получаем случайный прокси из списка https://github.com/TheSpeedX/PROXY-List/blob/master/http.txt
    :param random_proxy:
    :return: str or list
    """
    url = 'https://raw.githubusercontent.com/TheSpeedX/SOCKS-List/master/http.txt'
    data = get_requests(url, header=None, proxy=None, cookies=None)
    if random_proxy:
        return random.choice(data.split())
    return data.split()


def get_header():
    return {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:83.0) Gecko/20100101 Firefox/83.0'}


def get_cookies(UID='1600358281310099714', COOK_ID='1606041181', JSESSIONID='C1ED0DAB9D680448E717FF3B48FCCCE5'):
    """
    :param UID:
    :param COOK_ID:
    :param JSESSIONID:
    :return: list
    """
    cookies = {
        'uniI18nLang': 'RUS',
        '_ym_uid': UID,
        '_ym_d': COOK_ID,
        'JSESSIONID': JSESSIONID,
        '_ym_visorc': 'w',
        '_ym_isad': '2',
    }
    return cookies


class Parser:
    """ Мультипоточный парвсер данных(ЕГРЮЛ) с сайта сайта налоговой
        :function
           - get_proxy() - получаем случайный прокси из списка
                           https://github.com/TheSpeedX/PROXY-List/blob/master/http.txt
                           Зависимость от requests_standart()
           - parser() - начальный парсинг списка по условию поиска
           - full() - парсинг по ИНН
           - roscom() - парсинг данных Роскомнадзора
    """

    def get_data(self):
        pass

    def get_full(self):
        pass

    def get_roscom(self):
        pass



# points 
### JuanJo Ramírez, mail: juan.moreno@ues.edu.sv

import math #nos auxiliaremos de esta librería

class Point:

    def __init__(self, xCoord=0, yCoord=0):
        self.__xCoord = xCoord
        self.__yCoord = yCoord

    # coordenada x
    def get_xCoord(self):
        return self.__xCoord

    # definir x
    def set_xCoord(self, xCoord):
        self.__xCoord = xCoord

    # coordenada y
    def get_yCoord(self):
        return self.__yCoord

    # definir y
    def set_yCoord(self, yCoord):
        self.__yCoord = yCoord

    # posicion
    def get_position(self):
        return self.__xCoord, self.__yCoord

    # cambiar x & y por p & q
    def move(self, p, q):
        self.__xCoord += p
        self.__yCoord += q

    # sobrecargar el operador + 
    def __add__(self, point_ov):
        return Point(self.__xCoord + point_ov.__xCoord, self.__yCoord + point_ov.__yCoord)

    # sobrecargar el operador -
    def __sub__(self, point_ov):
        return Point(self.__xCoord - point_ov.__xCoord, self.__yCoord - point_ov.__yCoord)

    # sobrecargar el operador <
    def __lt__(self, point_ov):
        return math.sqrt(self.__xCoord ** 2 + self.__yCoord ** 2) < math.sqrt(point_ov.__xCoord ** 2 + point_ov.__yCoord ** 2)

    # sobrecargar el operador >
    def __gt__(self, point_ov):
        return math.sqrt(self.__xCoord ** 2 + self.__yCoord ** 2) > math.sqrt(point_ov.__xCoord ** 2 + point_ov.__yCoord ** 2)

    # sobrecargar el operador <=
    def __le__(self, point_ov):
        return math.sqrt(self.__xCoord ** 2 + self.__yCoord ** 2) <= math.sqrt(point_ov.__xCoord ** 2 + point_ov.__yCoord ** 2)

    # sobrecargar el operador >=
    def __ge__(self, point_ov):
        return math.sqrt(self.__xCoord ** 2 + self.__yCoord ** 2) >= math.sqrt(point_ov.__xCoord ** 2 + point_ov.__yCoord ** 2)

    # sobrecargar el operador ==
    def __eq__(self, point_ov):
        return math.sqrt(self.__xCoord ** 2 + self.__yCoord ** 2) == math.sqrt(point_ov.__xCoord ** 2 + point_ov.__yCoord ** 2)

point1 = Point(2, 4)
point2 = Point(12, 8)

print("point1 < point2:", point1 < point2)
print("point1 > point2:", point1 > point2)
print("point1 <= point2:", point1 <= point2)
print("point1 >= point2:", point1 >= point2)
print("point1 == point2:", point1 == point2)

from abc import ABC, abstractmethod
import math

class Figura(ABC):
    @abstractmethod
    def calcular_perimetro(self) -> float:
        pass

    @abstractmethod
    def calcular_area(self) -> float:
        pass

    @abstractmethod
    def obtener_nombre(self) -> str:
        pass

class HexagonoRegular(Figura):
    def __init__(self, lado: float):
        self.lado = lado

    def calcular_perimetro(self) -> float:
        return 6 * self.lado

    def calcular_area(self) -> float:
        return (3 * math.sqrt(3) * (self.lado ** 2)) / 2

    def obtener_nombre(self) -> str:
        return "Hexágono"

if __name__ == "__main__":
    h = HexagonoRegular(3)
    print(h.obtener_nombre())
    print(f"Perímetro: {h.calcular_perimetro():.2f}")
    print(f"Área: {h.calcular_area():.2f}")

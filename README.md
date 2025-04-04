# crop-simulation
import random
import time

class Crop:
    def __init__(self, name, growth_time, yield_amount):
        self.name = name
        self.growth_time = growth_time  # Time in seconds for simulation
        self.yield_amount = yield_amount
        self.grown = False

    def grow(self):
        print(f"🌱 Planting {self.name}... Waiting {self.growth_time} seconds for growth.")
        time.sleep(self.growth_time)
        self.grown = True
        print(f"✅ {self.name} is fully grown! Ready for harvest.")

    def harvest(self):
        if self.grown:
            print(f"🌾 Harvesting {self.yield_amount} units of {self.name}!")
            self.grown = False  # Reset for new planting
        else:
            print(f"⏳ {self.name} is not ready yet!")

# Example usage
def main():
    wheat = Crop("Wheat", 3, random.randint(5, 10))
    corn = Crop("Corn", 5, random.randint(8, 15))
    
    wheat.grow()
    wheat.harvest()
    
    corn.grow()
    corn.harvest()

if __name__ == "__main__":
    main()
ytr

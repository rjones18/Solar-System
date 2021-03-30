# Solar-System
In this assignment I used use your knowledge of inheritance and instance methods to make a soalr syestem! below is my final code: 

```
class Body:
  def __init__(self, name, mass):
    self.name = name
    self.mass = mass

class Star(Body):
  def __init__(self, name, mass, _type):
    super().__init__(name, mass)
    self._type = _type

class Planet(Body):
  def __init__(self, name, mass, day_length, year_length):
    super().__init__(name, mass)
    self.day_length = day_length
    self.year_length = year_length

class Moon(Body):
  def __init__(self, name, mass, month_length, orbit_planet):
    super().__init__(name, mass)
    self.month_length = month_length
    self.orbit_planet = orbit_planet

class System:
  def __init__(self):
    self.bodies = []
    

  
  def add(self,bodies):
    self.bodies.append(bodies)

  def total_mass(self):
    total = 0
    for body in self.bodies:
      total += body.mass
    return total

def main():
  # Create the solar system and its bodies
  sun   = Star('Sun', 200, 'G-Type' ) # Use the name 'Sun', mass of 200, and type of 'G-Type'
  earth = Planet('Earth', 150, 24, 365) # Use the name 'Earth', mass of 150, day_length of 24, and year_length of 365
  luna  = Moon('Luna', 100, 30, 'Earth') # Use the name 'Luna', mass of 100, month_length of 30, and orbit_planet of earth
  solar_system = System()
  solar_system.add(earth)
  solar_system.add(sun)
  solar_system.add(luna)

  # Print each body in the solar system to see if they have been added correctly
  for body in solar_system.bodies:
    print(body.name)

  # Checking to see that total mass is correct
  print(solar_system.total_mass())

main()



```

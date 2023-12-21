class ParkingLot:
    def __init__(self, capacity_per_level=20):
        self.capacity_per_level = capacity_per_level
        self.levels = {'A': {}, 'B': {}}
        self.available_spots = {'A': list(range(1, 21)), 'B': list(range(21, 41))}

    def assign_parking_spot(self, vehicle_number):
        if not self.available_spots['A'] and not self.available_spots['B']:
            return "Parking is full."

        level, spot = self.get_next_available_spot()
        self.levels[level][vehicle_number] = spot
        return {"level": level, "spot": spot}

    def get_parking_spot(self, vehicle_number):
        for level, spots in self.levels.items():
            if vehicle_number in spots:
                return {"level": level, "spot": spots[vehicle_number]}
        return "Vehicle not found in the parking lot."

    def unpark_vehicle(self, vehicle_number):
        for level, spots in self.levels.items():
            if vehicle_number in spots:
                spot = spots.pop(vehicle_number)
                self.available_spots[level].append(spot)
                return {"level": level, "spot": spot}

        return "Vehicle not found in the parking lot."

    def get_next_available_spot(self):
        for level, spots in self.available_spots.items():
            if spots:
                return level, spots.pop(0)

        return None, None


def main():
    parking_lot = ParkingLot()

    while True:
        print("\n1. Assign Parking Spot\n2. Retrieve Parking Spot\n3. Unpark Vehicle\n4. Exit")
        choice = int(input("Enter your choice: "))

        if choice == 1:
            vehicle_number = input("Enter vehicle number: ")
            result = parking_lot.assign_parking_spot(vehicle_number)
            print(f"Parking Spot Assigned: {result}")

        elif choice == 2:
            vehicle_number = input("Enter vehicle number: ")
            result = parking_lot.get_parking_spot(vehicle_number)
            print(f"Vehicle Parking Spot: {result}")

        elif choice == 3:
            vehicle_number = input("Enter vehicle number: ")
            result = parking_lot.unpark_vehicle(vehicle_number)
            print(f"Vehicle Unparked from: {result}")

        elif choice == 4:
            break

        else:
            print("Invalid choice. Please enter a valid option.")

if __name__ == "__main__":
    main()

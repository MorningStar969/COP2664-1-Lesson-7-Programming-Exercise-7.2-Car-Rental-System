# COP2664-1-Lesson-7-Programming-Exercise-7.2-Car-Rental-System
This is a GitHub repository link for the second Programming Exercise of Module 7.

// This program is used for a rental car system that lists down the fleet of vehicles available for rent.

enum VehicleStatus {
    case available
    case rented
    case maintenance
}
// This enum is used to define the status of the vehicles in the fleet.

struct VehicleDetails {
    let make: String
    let model: String
    let year: Int
}
// VehicleDetails is a struct that contains the make, model, and year of the vehicle.

class Vehicle {
    var id: Int
    var type: String
    var status: VehicleStatus
    var details: VehicleDetails
  // Vehicle is a class that represents a vehicle in the fleet. It has an ID, type, status, and details.
    
  init(id: Int, type: String, status: VehicleStatus, details: VehicleDetails) {
        self.id = id
        self.type = type
        self.status = status
        self.details = details
  }
  // This is the initializer for the Vehicle class. It takes in an ID, type, status, and details as arguments and assigns them to the corresponding properties.
    func rent() {
        if status == .available {
            status = .rented
        }
    }
    func returnToFleet() {
        if status == .rented {
            status = .available
        }
    }
    func sendToMaintenance() {
        if status == .rented {
            status = .maintenance
        }
    }
  // These methods are used to rent, return, and send the vehicle to maintenance.
    func displayDetails() {
        print("Vehicle ID: \(id)")
        print("Type: \(type)")
        print("Status: \(status)")
        print("Make: \(details.make)")
        print("Model: \(details.model)")
        print("Year: \(details.year)")
    }
}
// This class represents a vehicle in the fleet. It has an ID, type, status, and details.

let vehicle1 = Vehicle(id: 103, type: "SUV", status: .available, details: VehicleDetails(make: "Kia", model: "Sportage", year: 2025))
let vehicle2 = Vehicle(id: 127, type: "Car", status: .rented, details: VehicleDetails(make: "Chevrolet", model: "Corvette Z06", year: 2019))
let vehicle3 = Vehicle(id: 168, type: "Van", status: .maintenance, details: VehicleDetails(make: "Nissan", model: "NV Passenger", year: 2021))
// These are the three vehicles in the fleet.
vehicle1.rent()
vehicle2.returnToFleet()
vehicle3.sendToMaintenance()
vehicle1.displayDetails()
vehicle2.displayDetails()
vehicle3.displayDetails()
// These lines of code rent, return, and send the vehicles to maintenance, and then display the details of each vehicle.

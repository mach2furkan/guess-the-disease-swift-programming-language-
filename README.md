# guess-the-disease-swift-programming-language-
this  swift code can guess your disease 
      //
      //  main.swift
      //  without go ddoctor
      //
      //  Created by Furkan Aşkın on 13.03.2024.
      //

    import Foundation

    // Define a struct to represent a symptom
    struct Symptom {
    let name: String
    var severity: Int // You can adjust the severity scale as needed
    }

    // Define a struct to represent a patient
    struct Patient {
    var symptoms: [Symptom]
    }

    // Function to predict diseases based on symptoms
    func predictDisease(for patient: Patient) -> String {
    // Perform disease prediction logic here
    // This could involve querying a medical database or using machine learning models
    
    // For now, let's just return a placeholder result
    return "Placeholder disease prediction"
    }

    // Main function to simulate the application
    func main() {
    print("Welcome to Disease Predictor")
    print("Please enter the symptoms one by one. Type 'done' when finished.")
    
    var symptoms = [Symptom]()
    var doneEnteringSymptoms = false
    
    while !doneEnteringSymptoms {
        print("Enter symptom name:")
        if let symptomName = readLine(), !symptomName.isEmpty {
            if symptomName.lowercased() == "done" {
                doneEnteringSymptoms = true
            } else {
                print("Enter symptom severity (1-10):")
                if let severityInput = readLine(), let severity = Int(severityInput) {
                    let symptom = Symptom(name: symptomName, severity: severity)
                    symptoms.append(symptom)
                } else {
                    print("Invalid severity input. Please enter a number between 1 and 10.")
                }
            }
        } else {
            print("Invalid input. Please enter a symptom name.")
        }
    }
    
    let patient = Patient(symptoms: symptoms)
    let predictedDisease = predictDisease(for: patient)
    print("Predicted disease based on entered symptoms: \(predictedDisease)")
    }

    // Call the main function to start the application
    main()

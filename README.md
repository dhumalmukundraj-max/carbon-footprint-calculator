 EMISSION_FACTORS = {
    "car": 0.21,      # kg CO2 per km
    "bike": 0.05,
    "bus": 0.10,
    "electricity": 0.82,  # kg CO2 per unit
    "lpg": 2.98       # kg CO2 per kg
}

# User inputs
print("---- Carbon Footprint Calculator ----")

vehicle = input("Enter transport type (car/bike/bus): ").lower()
distance = float(input("Enter distance travelled (km per day): "))

electricity_units = float(input("Enter electricity usage (units per month): "))
lpg_used = float(input("Enter LPG usage (kg per month): "))

# Calculations
transport_emission = distance * EMISSION_FACTORS.get(vehicle, 0)
electricity_emission = electricity_units * EMISSION_FACTORS["electricity"]
lpg_emission = lpg_used * EMISSION_FACTORS["lpg"]

total_emission = transport_emission + electricity_emission + lpg_emission

# Output
print("\n--- Carbon Footprint Result ---")
print(f"Transport CO2 Emission: {transport_emission:.2f} kg")
print(f"Electricity CO2 Emission: {electricity_emission:.2f} kg")
print(f"LPG CO2 Emission: {lpg_emission:.2f} kg")

print(f"\n🌍 Total Carbon Footprint: {total_emission:.2f} kg CO2 per month")

# Suggestions
print("\n--- Eco-Friendly Suggestions ---")
if total_emission > 300:
    print("• Use public transport or carpool")
    print("• Reduce electricity usage")
    print("• Switch to renewable energy if possible")
else:
    print("• Great job! Keep following sustainable habits 🌱")
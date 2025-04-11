def loan_calculator():
    print("Loan Calculator (₹)")

    # Inputs
    loan_amount = float(input("Enter loan amount (in ₹): "))
    annual_rate = float(input("Enter annual interest rate (in %): "))
    years = int(input("Enter loan term (in years): "))

    # Convert annual rate to monthly and years to months
    monthly_rate = annual_rate / 100 / 12
    months = years * 12

    # EMI Calculation
    if monthly_rate == 0:
        monthly_payment = loan_amount / months
    else:
        monthly_payment = loan_amount * monthly_rate * (1 + monthly_rate) ** months / ((1 + monthly_rate) ** months - 1)

    total_payment = monthly_payment * months
    total_interest = total_payment - loan_amount

    # Output
    print(f"\nMonthly EMI: ₹{monthly_payment:,.2f}")
    print(f"Total Payment: ₹{total_payment:,.2f}")
    print(f"Total Interest: ₹{total_interest:,.2f}")

# Run the calculator
loan_calculator()

# week-4
Scripts for week 4
def calculate_distance(initial_height, num_bounces):
    total_distance = initial_height
    bounce_height = initial_height

    for _ in range(num_bounces):
        bounce_height *= 0.6
        total_distance += bounce_height * 2

    return total_distance


initial_height = float(input("Enter the initial height from which the ball is dropped (in feet): "))
num_bounces = int(input("Enter the number of times the ball will continue bouncing: "))

distance = calculate_distance(initial_height, num_bounces)
print(f"The total distance traveled by the ball after {num_bounces} bounce(s) is {distance} feet.")

def calculate_pi_approximation(iterations):
    approximation = 0
    sign = 1

    for i in range(1, iterations * 2, 2):
        approximation += sign * (1 / i)
        sign *= -1

    approximation *= 4
    return approximation
num_iterations = int(input("Enter the number of iterations to approximate π: "))
pi_approximation = calculate_pi_approximation(num_iterations)
print(f"The approximation of π after {num_iterations} iterations is: {pi_approximation}")

def generate_salary_schedule(starting_salary, percentage_increase, num_years):
    schedule = []
    current_salary = starting_salary

    for year in range(1, num_years + 1):
        schedule.append((year, current_salary))
        current_salary += current_salary * (percentage_increase / 100)

    return schedule
starting_salary = float(input("Enter the starting salary for teachers: $"))
percentage_increase = float(input("Enter the percentage increase per year: "))
num_years = int(input("Enter the number of years in the salary schedule: "))

salary_schedule = generate_salary_schedule(starting_salary, percentage_increase, num_years)
print("Salary Schedule:")
print("----------------")
print("Year\tSalary")
for year, salary in salary_schedule:
    print(f"{year}\t${salary:,.2f}")

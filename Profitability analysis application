import matplotlib.pyplot as plt

def get_input():
    items = []
    costs = []
    revenues = []

    print("Enter the number of items:")
    n = int(input())

    for i in range(n):
        print(f"\nEnter details for item {i+1}:")
        item = input("Item Name: ")
        cost = float(input("Cost ($): "))
        revenue = float(input("Revenue ($): "))

        items.append(item)
        costs.append(cost)
        revenues.append(revenue)

    return items, costs, revenues

def calculate_profitability(items, costs, revenues):
    profits = []
    margins = []
    for c, r in zip(costs, revenues):
        profit = r - c
        margin = (profit / r) * 100 if r != 0 else 0
        profits.append(profit)
        margins.append(margin)
    return profits, margins

def print_report(items, costs, revenues, profits, margins):
    print("\n--- Profitability Report ---")
    print(f"{'Item':<15}{'Cost($)':<10}{'Revenue($)':<12}{'Profit($)':<10}{'Margin(%)':<10}")
    for i in range(len(items)):
        print(f"{items[i]:<15}{costs[i]:<10.2f}{revenues[i]:<12.2f}{profits[i]:<10.2f}{margins[i]:<10.2f}")

    max_profit = max(profits)
    min_profit = min(profits)
    most_profitable = items[profits.index(max_profit)]
    least_profitable = items[profits.index(min_profit)]

    print(f"\nMost Profitable Item: {most_profitable} (${max_profit:.2f})")
    print(f"Least Profitable Item: {least_profitable} (${min_profit:.2f})")

def plot_profit(items, profits):
    colors = ['green' if p >= 0 else 'red' for p in profits]
    plt.bar(items, profits, color=colors)
    plt.title("Profit per Item")
    plt.xlabel("Items")
    plt.ylabel("Profit ($)")
    plt.grid(axis='y')
    plt.show()

def main():
    items, costs, revenues = get_input()
    profits, margins = calculate_profitability(items, costs, revenues)
    print_report(items, costs, revenues, profits, margins)
    plot_profit(items, profits)

if __name__ == "__main__":
    main()

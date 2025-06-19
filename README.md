
class TicketBookingSystem:
    def __init__(self):
        self.shows = {
            "Movie A": {"seats": 50, "price": 150},
            "Movie B": {"seats": 40, "price": 120},
            "Movie C": {"seats": 30, "price": 100}
        }
        self.bookings = []

    def view_shows(self):
        print("\nAvailable Shows:")
        for movie, details in self.shows.items():
            print(f"- {movie}: {details['seats']} seats available @ ₹{details['price']} per ticket")

    def book_ticket(self):
        self.view_shows()
        movie = input("\nEnter the movie name you want to book: ").strip()
        if movie not in self.shows:
            print("Invalid movie name.")
            return

        try:
            num_tickets = int(input("Enter number of tickets: "))
        except ValueError:
            print("Invalid number.")
            return

        if num_tickets <= 0:
            print("Number of tickets must be more than 0.")
            return

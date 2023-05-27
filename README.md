# TokenRing
class TokenRing:
    def __init__(self):
        self.token = 0
    
    def pass_token(self, sender, receiver, data):
        n = len(nodes)
        print("Token Passing:", end="")
        for i in range(self.token, sender):
            print(" " + str(i) + "->", end="")
        print(" " + str(sender))
        print("Sender: " + str(sender) + " Sending Data: " + str(data))
        
        for i in range(sender, (receiver + 1) % n):
            print("Data: " + str(data) + " Forwarded By: " + str(i))
        
        print("Receiver: " + str(receiver) + " Received The Data: " + str(data))
        
    def run(self):
        nodes = []
        
        n = int(input("Enter Number Of Nodes You Want In The Ring: "))
        
        print("Ring Formed Is As Below:")
        for i in range(n):
            print(str(i) + " ", end="")
        print("0")
        
        choice = 0
        
        while choice == 1:
            sender = int(input("Enter Sender: "))
            receiver = int(input("Enter Receiver: "))
            data = int(input("Enter Data To Send: "))
            
            self.pass_token(sender, receiver, data)
            
            self.token = sender
            
            choice = int(input("Do You Want To Send Data Again? If YES Enter 1, If NO Enter 0: "))

token_ring = TokenRing()
token_ring.run()

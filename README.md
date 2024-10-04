class PowerTailgate:
    def __init__(self):
        self.is_open = False  # 尾門的初始狀態為關閉
        self.is_obstructed = False  # 初始無障礙物

    def open_tailgate(self):
        """開啟尾門"""
        if self.is_open:
            print("Tailgate is already open.")
        elif self.is_obstructed:
            print("Obstacle detected! Cannot open tailgate.")
        else:
            self.is_open = True
            print("Tailgate is opening...")

    def close_tailgate(self):
        """關閉尾門"""
        if not self.is_open:
            print("Tailgate is already closed.")
        elif self.is_obstructed:
            print("Obstacle detected! Cannot close tailgate.")
        else:
            self.is_open = False
            print("Tailgate is closing...")

    def detect_obstacle(self, obstacle_present):
        """檢測是否有障礙物"""
        self.is_obstructed = obstacle_present
        if self.is_obstructed:
            print("Obstacle detected! Operation blocked.")
        else:
            print("No obstacle detected.")

    def status(self):
        """顯示尾門的當前狀態"""
        state = "open" if self.is_open else "closed"
        print(f"Tailgate is currently {state}.")

# 創建電動尾門對象
tailgate = PowerTailgate()

# 模擬操作
tailgate.status()
tailgate.open_tailgate()

# 模擬檢測障礙物
tailgate.detect_obstacle(True)
tailgate.close_tailgate()

# 移除障礙物後再次操作
tailgate.detect_obstacle(False)
tailgate.close_tailgate()

# 最後檢查狀態
tailgate.status()
# PowerTailgate

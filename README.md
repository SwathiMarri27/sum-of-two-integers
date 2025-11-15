# sum-of-two-integers
class Solution(object):
    def getSum(self, a, b):
        # 32-bit mask
        MASK = 0xFFFFFFFF
        MAX_INT = 0x7FFFFFFF

        while b != 0:
            # Calculate carry
            carry = (a & b) & MASK

            # Sum without carry
            a = (a ^ b) & MASK

            # Shift carry
            b = (carry << 1) & MASK

        # If a is negative, convert to Python negative
        return a if a <= MAX_INT else ~(a ^ MASK)

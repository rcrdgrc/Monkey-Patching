class Array
  def span 
    return nil if self.empty?

    self.max - self.min
  end

  def average 
    if self == []
        return nil
    end
       self.sum  / (self.length * 1.0)
  end

  def median
    if self == []
        return nil
    end
   sorted = self.sort!
    l = self.length
   if l.odd?
      sorted[(l / 2)]  
   elsif l.even?
        [sorted[l / 2], sorted[(l / 2) - 1]].average
   end
  end

  def counts
    hash = Hash.new(0)
        self.each { |char| hash[char] += 1}
    return hash
  end

# Part 2

  def my_count(value)
    count = self.counts 
        count[value]
  end

  def my_index(value)
    i = 0
    while i < self.length
        if self[i] == value
            return i
        
        end
        i += 1
    end
  end

  def my_uniq
    array = []
    count = self.counts
    count.each do |k, v|
        array << k

    end
    array
  end

  def my_transpose
    new_array = []
    (0...self.length).each do |row|
        array = []
        (0...self.length).each do |col|
            array << self[col][row]
        end
        new_array << array
    end
   new_array
  end
end

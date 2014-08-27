Cinema_review
=============

#Just a cinema reviews developed in ruby
movies = {
    nayagan: 5, mangatha: 4
}
puts "Enter the option"
puts "'add' to add the new movie"
puts "'update'to enter the new rating of the existing movie"
puts "'delete'to delete the movie from rating"
puts "'display' to see all movies review"
puts "'quit' to exit"
choice=gets.chomp
case choice
when 'add'

puts "Add movie title"
title=gets.chomp
if movies[title.to_sym].nil?
    
puts"add the rating to #{title}"
rating=gets.chomp
movies[title.to_sym]= rating.to_i
puts "Thanks for the update. The review of #{title} is added as #{movies[title.intern]}"
else
    puts "#{title} is already present. Latest review of #{title} is #{movies[title.to_sym]}"
end
when 'update'
puts "Enter the movie name to update the rating"
title=gets.chomp
if movies[title.to_sym].nil?
    puts "The review of #{title} is not avail. Kindly add the rating through add option"
else
    puts "Enter the new rating of #{title}"
    rating = gets.chomp
    movies[title.to_sym]=rating.to_i
    puts "The #{title} is updated as #{movies[title.to_sym]}"
end
when 'display'
movies.each do  |movie,rating| puts "#{movie}: #{rating}" 
end
when 'delete'
puts "Enter the movie to be deleted"
title=gets.chomp
if movies[title.to_sym].nil?
    puts "No such movie is found"
else
    movies.delete(title.to_sym)
    puts "Action successful"
end
when 'quit'
exit

else
    puts "error"
end

puts movies

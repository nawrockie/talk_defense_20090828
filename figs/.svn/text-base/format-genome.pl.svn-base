$usage = "perl format-genome.pl <genome fa file> <start posn> <end posn> <nchars per line>\n";
if(scalar(@ARGV) != 4) { die $usage; }

($genome, $start, $end, $nchars) = @ARGV;

open(IN, $genome) || die ("ERROR couldn't open $genome");
while($line = <IN>) { 
    chomp $line;
    $line =~ s/^\s+//;
    $line =~ s/\s+$//;
    if($line !~ m/^\>/) { 
	$genome .= $line;
    }
}
close(IN);

@genomeA = split("", $genome);

$nchars_printed = 0;
for($i = ($start-1); $i <= ($end-1); $i++) { 
    printf("$genomeA[$i]");
    $nchars_printed++;
    if((($nchars_printed) % $nchars) == 0) { 
	printf("\n");
    }
}
#printf("\n");

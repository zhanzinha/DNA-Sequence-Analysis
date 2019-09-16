# DNA-Sequence-Analysis

def get_length(dna):
    """ (str) -> int

    Return the length of the DNA sequence dna.

    >>> get_length('ATCGAT')
    6
    >>> get_length('ATCG')
    4
    """
    chars=0
    for char in dna:
        chars = chars + 1
    return chars



def is_longer(dna1, dna2):
    """ (str, str) -> bool

    Return True if and only if DNA sequence dna1 is longer than DNA sequence
    dna2.

    >>> is_longer('ATCG', 'AT')
    True
    >>> is_longer('ATCG', 'ATCGGA')
    False
    """
    return dna1>dna2



def count_nucleotides(dna, nucleotide):
    """ (str, str) -> int

    Return the number of occurrences of nucleotide in the DNA sequence dna.

    >>> count_nucleotides('ATCGGC', 'G')
    2
    >>> count_nucleotides('ATCTA', 'G')
    0
    """
    chars=0
    for char in dna:
        if char in nucleotide:
            chars = chars + 1
    return chars    
    


def contains_sequence(dna1, dna2):
    """ (str, str) -> bool

    Return True if and only if DNA sequence dna2 occurs in the DNA sequence
    dna1.

    >>> contains_sequence('ATCGGC', 'GG')
    True
    >>> contains_sequence('ATCGGC', 'GT')
    False

    """
    if dna1.find(dna2) >0:
        return True
    
    return False


def is_valid_sequence(dna):

    """ (str) -> bool

    Return True if and only if the DNA sequence is valid with "ATCG"
    in the sequence. Doesn't matter the sequence.
    >>>is_valid_sequence("ATCG")
    True

    >>>is_valid_sequence("RFGS")
    False

    """

    is_valid_sequence = True
    valid="ATCG"

    for char in dna:
        if char not in valid:
            return False
    return is_valid_sequence



def insert_sequence(dna1,dna2,index):

    """ (str, str, int) -> str

    Return a sequence with dna2 in the desired index of dna1

    >>>insert_sequence("CCGG","AT",2)
    "CCATGG"

    >>>


    """

    return dna1[:index]+dna2+dna1[index:]

    
    



def get_complement(nucleotide):

    """ (str) -> str

    Returns the complement of the nucleotide

    >>>get_complement('A')
    'T'

    >>>get_complement('C')
    'G' 

    """

    if nucleotide in 'A':
        return 'T'
    elif nucleotide in 'T':
        return 'A'
    elif nucleotide in 'C':
        return 'G'
    elif nucleotide in 'G':
        return 'C'
    elif nucleotide in "":
        return 'please insert a nucleotide'
    else:
        return 'invalid'

##    out=""
##    if not is_valid_sequence(nucleotide):
##        return False
##    if not get_length(nucleotide) == 1:
##        return False
##    
##    for char in nucleotide:
##        if char in "A":
##            out = out + "T"
##        if char in "T":
##            out = out + "A"
##        if char in "G":
##            out = out + "C"
##        if char in "C":
##            out = out + "G"
##
##    return out

    


def get_complementary_sequence(dna):

    """ (str) -> str
    Returns the complement of the DNA sequence

    >>>get_complementary_sequence("AGCT")
    'TCGA'

    >>>get_complementary_sequence("TTGGCCAA")
    'AACCGGTT'

    """
    displayed=""
    if not is_valid_sequence(dna):
        return False

    for char in dna:
        displayed = displayed + get_complement(char)

    return displayed

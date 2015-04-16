 public boolean isValid(String s) {
       Stack<Character> stack = new Stack<>();
		char[] ch = s.toCharArray();
		if (ch.length % 2 != 0) {
			return false;
		}
		for (int i = 0; i < ch.length; i++) {
			char c = ch[i];
			if (c == '(' || c == '[' || c == '{') {
				stack.push(c);
			} else if (c == ')' || c == ']' || c == '}') {
				if (stack.size() == 0) {
					return false;
				}
				char cpop = stack.pop();
				if ((cpop == '(' && c == ')') || (cpop == '[' && c == ']')
						|| (cpop == '{' && c == '}')) {
					continue;
				}
				return false;
			}

		}
		return stack.empty();
    }
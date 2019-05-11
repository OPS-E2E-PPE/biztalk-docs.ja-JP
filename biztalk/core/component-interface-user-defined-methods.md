---
title: コンポーネント インターフェイス ユーザー定義メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, user-defined methods
- user-defined methods, component interface
- custom component interfaces, limitations
- collection limitations
- custom methods, samples
- samples, custom methods
- component interfaces, limitations for custom CI
ms.assetid: e4b15889-35ff-44aa-819d-eade9690bdd6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1574a73b45f5048910d5df8fee43d75502c2938b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356719"
---
# <a name="component-interface-user-defined-methods"></a>コンポーネント インターフェイス ユーザー定義メソッド
Microsoft BizTalk Adapter for PeopleSoft Enterprise では、コンポーネント インターフェイス ユーザー定義メソッドをサポートしています。 署名は、フォームのことです。  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 それぞれの文字の説明は次のとおりです。  
  
- `parameter1`、`parameter2`は入力パラメーターです。  
  
- `myRet` 戻り値です。  
  
  パラメーターは、メソッドへの入力パラメーターにできるだけです。 1 つの値は、戻りパラメーターとしてメソッドから返さことができます。  
  
> [!NOTE]
>  ユーザー定義メソッドを含むコンポーネント インターフェイスは、PeopleSoft にのみが`Get`機能を無効にします。 コンポーネント インターフェイスにキーがある場合は、カスタム メソッドは機能しません。  
  
## <a name="custom-ci-limitation"></a>カスタム CI の制限  
 BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスでキーを持っていないこと、カスタム PeopleSoft メソッドを処理できます。 コンポーネント インターフェイスにキーがある場合は、カスタム メソッドは機能しません。  
  
### <a name="workaround"></a>回避策  
 無効なキーを呼び出しのパラメーターの一部として、キーが組み込まれている新しいカスタム メソッドを作成、新しいコンポーネント インターフェイスを作成します。 たとえばは USER_PROFILE コンポーネント インターフェイスで SetPassword カスタム メソッドを使用できます。ただし USER_PROFILE には、キーがあります。 キーのない新しいコンポーネント インターフェイスを作成し、新しいコンポーネント インターフェイスでカスタム メソッドを作成できます。 このメソッドは、2 つのパラメーター、ユーザー ID とパスワードを受け入れるとします。 カスタム メソッドでした USER_PROFILE を呼び出し、 `Get` 、呼び出す`SetPassword`します。 詳細については、PeopleSoft のドキュメントを参照してください。  
  
 Peoplesoft の制限により`Date`、 `DateTime`、および`Time`クライアント コードで文字列としてユーザー定義メソッドに出現する型がマップされます。  
  
## <a name="collection-limitation"></a>コレクションの制限  
 ユーザー定義のメソッドは、コレクション、または複数を返すことはできません、API オブジェクトでは一般に、します。 これは、文字列や数値などの単純型を返すことを意味します。 正しい形式に項目を抽出する文字列を解析する XML 文字列としてコレクションを送信して、クライアントをプログラミングでこの制限を回避取得できます。 この回避策の例を参照する GET_CI_INFO カスタム コンポーネント インターフェイスを確認することができます。  
  
## <a name="sample-custom-method"></a>サンプル カスタム メソッド  
 次基本的なカスタム メソッド SayHello を使用すると、カスタム メソッドを使用してコンポーネント インターフェイスの機能をテストします。  
  
 次の PeopleCode 関数は、ACB_EMPLOYEE という名前の PeopleSoft コンポーネント インターフェイスのユーザー定義メソッドです。 このサンプルは、戻り値が文字列を返します**こんにちは**後に、入力パラメーターの値。  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  (1 つのコマンドを使用) と同時に複数のテーブルを変更するには、別のコンポーネント インターフェイスを作成するか、コンポーネント インターフェイス ユーザー定義メソッドを作成します。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)
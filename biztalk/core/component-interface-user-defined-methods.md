---
title: "コンポーネント インターフェイス ユーザー定義メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 139117ffb26c8fec355dcfe481657817bc64bc0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="component-interface-user-defined-methods"></a>コンポーネント インターフェイス ユーザー定義メソッド
Microsoft BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスでユーザー定義メソッドをサポートします。 署名の形式は次のとおりです。  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 それぞれの文字の説明は次のとおりです。  
  
-   `parameter1`、`parameter2` は入力パラメーターです。  
  
-   `myRet` は戻り値です。  
  
 パラメーターに指定できるのは、メソッドへの入力パラメーターだけです。 戻りパラメーターとしてメソッドから返すことができるのは 1 つの値のみです。  
  
> [!NOTE]
>  ユーザー定義メソッドを含むコンポーネント インターフェイスは、有効な PeopleSoft `Get` 関数だけを保持している必要があります。 コンポーネント インターフェイスにキーがある場合は、カスタム メソッドは機能しません。  
  
## <a name="custom-ci-limitation"></a>カスタム CI の制限  
 BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスにキーが存在しない場合にのみ、カスタム PeopleSoft メソッドを処理できます。 コンポーネント インターフェイスにキーが存在すると、カスタム メソッドは動作しません。  
  
### <a name="workaround"></a>回避策  
 キーを含まない新しいコンポーネント インターフェイスを作成し、呼び出しパラメーターの一部としてキーを含む新しいカスタム メソッドを書きます。 たとえば、SetPassword カスタム メソッドは USER_PROFILE コンポーネント インターフェイスで使用できますが、USER_PROFILE にはキーがあります。 キーのない新しいコンポーネント インターフェイスを作成し、新しいコンポーネント インターフェイスにカスタム メソッドを作成します。 このメソッドで、ユーザー ID とパスワードの 2 つのパラメーターを受け取ります。 このカスタム メソッドは、`Get` を使用して USER_PROFILE を呼び出し、さらに `SetPassword` を呼び出します。 詳細については、PeopleSoft のドキュメントを参照してください。  
  
 PeopleSoft の制限により、ユーザー定義メソッドに使用される `Date`、`DateTime`、および `Time` の型は、クライアント コードの文字列に対応しています。  
  
## <a name="collection-limitation"></a>コレクションの制限  
 ユーザー定義メソッドでは、コレクションを返すことはできません。より一般的に、API オブジェクトを返せません。 したがって、返すことができるのは、文字列や数値などの単純な型だけです。 この制限を回避するには、コレクションを XML 文字列として送信し、クライアントが文字列を解析してアイテムを正しい形式で抽出するようにプログラミングします。 GET_CI_INFO カスタム コンポーネント インターフェイスを調べると、この対応策の例を確認できます。  
  
## <a name="sample-custom-method"></a>サンプル カスタム メソッド  
 次の基本的なカスタム メソッド SayHello を使用して、カスタム メソッドを使用するコンポーネント インターフェイスの機能性をテストできます。  
  
 次の PeopleCode 関数は、ACB_EMPLOYEE という名前の PeopleSoft コンポーネント インターフェイスのユーザー定義メソッドです。 このサンプルは、戻り値が文字列を返します**こんにちは**後に、入力パラメーターの値。  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  (1 つのコマンドで) 複数のテーブルを同時に変更するには、別のコンポーネント インターフェイスを作成するか、またはユーザー定義メソッドを含むコンポーネント インターフェイスを作成します。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)
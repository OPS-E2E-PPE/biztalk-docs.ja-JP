---
title: "ユーザー コード内の参照をメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a1584be-35fd-4dc2-a5a9-559300e67e0e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264f50da516f44d8fc87186614a79bb81aaf77ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-references-in-user-code"></a>ユーザー コードでのメッセージ参照
メッセージが構築された時点では、メッセージ ボックス データベースとコンピューターのメモリにメッセージ表現が存在します。 メッセージ参照を .NET オブジェクトまたは外部アセンブリに渡し、この .NET オブジェクトまたは外部アセンブリでコンピューターのメモリにあるメッセージ表現を変更することによってメッセージ割り当てを行った場合、BizTalk オーケストレーション エンジンではその変更が認識されません。  
  
 また、メッセージ ボックス データベース内のメッセージ表現に含まれるメッセージ部分データは、無効になりません。 メッセージ部分データには、次のモードがあります。  
  
-   XML ドキュメント表現  
  
-   オブジェクト表現  
  
-   ストリーム表現  
  
-   UnderlyingPart 表現  
  
 メッセージ部分データがどのようにメモリ内で表現されるかは、メッセージの構築と、種類が .NET クラスと XML スキーマ定義言語 (XSD) スキーマのどちらであるかによって異なります。 ただし、UnderlyingPart 表現は常に、メッセージ ボックス データベースを指すストリームになります。 BizTalk Server のメッセージは、メッセージ ボックス データベースにコミットされた後には変更できないため、オーケストレーション エンジンではメッセージ部分データの参照にはメッセージ ボックス データベース内のメッセージ表現が使用されます。  
  
> [!NOTE]
>  コミット済みのメッセージの各部について割り当てを行う場合、構築されたメッセージのメッセージ表現が既にメッセージ ボックス データベース内に存在する可能性があります。  
  
 たとえば、次のコードでは、メッセージ ボックス データベース内にあるメッセージ表現の UnderlyingPart データが送信されます。  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 上のユーザー コードではなく、次のようなコードを使用すれば、XmlDocument ドキュメントを XLANG のメッセージ変数に返すことができます。  
  
```  
Void A.test(ref XmlDocument xd) {…}  
XmlDocument B.test(XmlDocument xd) {…}  
construct m2 {  
               m2 = m1;  
               m2(myContextProperty) = “123”; // m2’s part data representation is the UnderlyingPart data of m1  
               A.test(ref m2.part); // orchestration engine has enough information to know it has to invalidate the UnderlyingPart MessageBox representation  
               // or  
               m2.part = B.test(m2.part); // orchestration engine has enough information to know it has to invalidate the UnderlyingPart MessageBox representation  
             }  
```
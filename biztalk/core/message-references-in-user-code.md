---
title: メッセージのユーザー コード内の参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a1584be-35fd-4dc2-a5a9-559300e67e0e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71e73eb9b953e514e48ae4e927ec3e4c104feb43
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972499"
---
# <a name="message-references-in-user-code"></a><span data-ttu-id="b17a5-102">ユーザー コードでのメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="b17a5-102">Message References in User Code</span></span>
<span data-ttu-id="b17a5-103">メッセージが構築された時点では、メッセージ ボックス データベースとコンピューターのメモリにメッセージ表現が存在します。</span><span class="sxs-lookup"><span data-stu-id="b17a5-103">When a message is constructed, a representation of the message is in the MessageBox database and another representation is in memory on the computer.</span></span> <span data-ttu-id="b17a5-104">メッセージ参照を .NET オブジェクトまたは外部アセンブリに渡し、この .NET オブジェクトまたは外部アセンブリでコンピューターのメモリにあるメッセージ表現を変更することによってメッセージ割り当てを行った場合、BizTalk オーケストレーション エンジンではその変更が認識されません。</span><span class="sxs-lookup"><span data-stu-id="b17a5-104">If you make the message assignment by passing a message reference to a .NET object or to an external assembly, and then the .NET object or the external assembly modifies the representation in memory on the computer, the BizTalk Orchestration Engine is not aware of the modification.</span></span>  
  
 <span data-ttu-id="b17a5-105">また、メッセージ ボックス データベース内のメッセージ表現に含まれるメッセージ部分データは、無効になりません。</span><span class="sxs-lookup"><span data-stu-id="b17a5-105">Moreover, the orchestration engine does not invalidate the message part data that is in the representation in the MessageBox database.</span></span> <span data-ttu-id="b17a5-106">メッセージ部分データには、次のモードがあります。</span><span class="sxs-lookup"><span data-stu-id="b17a5-106">Message part data has the following modes of representation:</span></span>  
  
- <span data-ttu-id="b17a5-107">XML ドキュメント表現</span><span class="sxs-lookup"><span data-stu-id="b17a5-107">XmlDocument representation</span></span>  
  
- <span data-ttu-id="b17a5-108">オブジェクト表現</span><span class="sxs-lookup"><span data-stu-id="b17a5-108">Object representation</span></span>  
  
- <span data-ttu-id="b17a5-109">ストリーム表現</span><span class="sxs-lookup"><span data-stu-id="b17a5-109">Stream representation</span></span>  
  
- <span data-ttu-id="b17a5-110">UnderlyingPart 表現</span><span class="sxs-lookup"><span data-stu-id="b17a5-110">UnderlyingPart representation</span></span>  
  
  <span data-ttu-id="b17a5-111">メッセージ部分データがどのようにメモリ内で表現されるかは、メッセージの構築と、種類が .NET クラスと XML スキーマ定義言語 (XSD) スキーマのどちらであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b17a5-111">How the message part data is represented in memory depends on the message construction and whether the type is a .NET class or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="b17a5-112">ただし、UnderlyingPart 表現は常に、メッセージ ボックス データベースを指すストリームになります。</span><span class="sxs-lookup"><span data-stu-id="b17a5-112">However, the UnderlyingPart representation is always a stream pointing into the MessageBox database.</span></span> <span data-ttu-id="b17a5-113">BizTalk Server のメッセージは、メッセージ ボックス データベースにコミットされた後には変更できないため、オーケストレーション エンジンではメッセージ部分データの参照にはメッセージ ボックス データベース内のメッセージ表現が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b17a5-113">Because messages in BizTalk Server are immutable after the message is committed to the MessageBox database, the orchestration engine uses the representation in the MessageBox database to reference message part data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b17a5-114">コミット済みのメッセージの各部について割り当てを行う場合、構築されたメッセージのメッセージ表現が既にメッセージ ボックス データベース内に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b17a5-114">A constructed message may already have a representation in the MessageBox database if you assign parts from a message that is already committed.</span></span>  
  
 <span data-ttu-id="b17a5-115">たとえば、次のコードでは、メッセージ ボックス データベース内にあるメッセージ表現の UnderlyingPart データが送信されます。</span><span class="sxs-lookup"><span data-stu-id="b17a5-115">For example, the following code sends the UnderlyingPart data from the representation in the MessageBox database:</span></span>  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 <span data-ttu-id="b17a5-116">上のユーザー コードではなく、次のようなコードを使用すれば、XmlDocument ドキュメントを XLANG のメッセージ変数に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b17a5-116">Instead of using the preceding user code, you can use code that is similar to the following to return an XmlDocument document to a Message XLANG variable:</span></span>  
  
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
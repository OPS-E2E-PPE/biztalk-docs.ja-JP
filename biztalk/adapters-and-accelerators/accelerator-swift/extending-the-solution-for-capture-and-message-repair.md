---
title: キャプチャおよびメッセージ修復のソリューションを拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2b4436906b1df913deec8b525143773dd43e4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979643"
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a><span data-ttu-id="98416-102">キャプチャおよびメッセージ修復のソリューションを拡張します。</span><span class="sxs-lookup"><span data-stu-id="98416-102">Extending the Solution for Capture and Message Repair</span></span>
<span data-ttu-id="98416-103">このヘルプに MT103 エンド ツー エンドのチュートリアルでは、失敗した SWIFT メッセージをサブスクライブする BizTalk オーケストレーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="98416-103">The MT103 End-to-End Tutorial in this Help shows you how to construct a BizTalk orchestration that subscribes to failed SWIFT messages.</span></span>  
  
 <span data-ttu-id="98416-104">MT103 エンド ツー エンドのチュートリアルのオーケストレーションでは、ヘルパー クラスの静的メソッドを使用して**ErrorExtractor**をエラーの部分と本文を文字列としてメッセージから抽出します。</span><span class="sxs-lookup"><span data-stu-id="98416-104">The orchestration in the MT103 End-to-End Tutorial uses the static methods of a helper class, **ErrorExtractor**, to extract the error part and body from the message as strings.</span></span> <span data-ttu-id="98416-105">オーケストレーションは、個別のファイルの部分を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="98416-105">The orchestration then writes the parts to separate files.</span></span>  
  
 <span data-ttu-id="98416-106">失敗したメッセージのエラーの一部がのシリアル化であるため、 **ErrorCollection**パイプライン コンポーネントによって構築された、コレクションを逆シリアル化して使用できますが、エラー報告と処理の多くを自動化します。</span><span class="sxs-lookup"><span data-stu-id="98416-106">Because the error part of the failed message is a serialization of the **ErrorCollection** constructed by the pipeline component, you can deserialize the collection and use it to automate more of the error reporting and handling.</span></span> <span data-ttu-id="98416-107">次の Microsoft[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]のコードが失敗したメッセージのエラー メッセージの部分を逆シリアル化し、コレクション内の解析エラーを反復処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="98416-107">The following Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] code fragment illustrates how to deserialize the error message part of a failed message and iterate over the parsing errors in the collection.</span></span> <span data-ttu-id="98416-108">コード フラグメントは、読みやすくするための名前空間の修飾が省略されます。</span><span class="sxs-lookup"><span data-stu-id="98416-108">The code fragment omits namespace qualifications for readability:</span></span>  
  
```  
// instantiate an appropriate XmlTextReader  
// xm contains the message  
string sError = ErrorExtractor.GetErrorPartAsString(xm);  
StringReader sRdr = new StringReader(sError);  
XmlTextReader xRdr = new XmlTextReader(sRdr);  
  
// deserialize the collection  
ErrorCollection eC = ErrorCollection.GetErrorCollection(xRdr);  
  
// loop over the parsing errors in the collection  
IEnumerator pEnum = eC.GetParseErrorEnumerator();  
while(pEnum.MoveNext())   
{  
  // pEnum.Current() returns a ParseError object for processing  
}  
  
```  
  
 <span data-ttu-id="98416-109">**ErrorCollection**エラーによって、すべてのコレクション内のエラーを反復処理する場合と同様に型を反復処理するメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98416-109">The **ErrorCollection** includes methods for iterating over errors by type as well as for iterating over all of the errors in the collection.</span></span> <span data-ttu-id="98416-110">詳細については、 **ErrorCollection**元のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98416-110">For more information about the **ErrorCollection**, see ErrorCollection Members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98416-111">参照</span><span class="sxs-lookup"><span data-stu-id="98416-111">See Also</span></span>  
 [<span data-ttu-id="98416-112">失敗したメッセージと ErrorCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="98416-112">Failed Messages and ErrorCollection Objects</span></span>](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)
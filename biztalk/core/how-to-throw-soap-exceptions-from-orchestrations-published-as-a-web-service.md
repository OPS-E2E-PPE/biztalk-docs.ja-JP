---
title: Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12c849d592a7cdce5968678f524ec15562830eba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333802"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a><span data-ttu-id="5beeb-102">Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法</span><span class="sxs-lookup"><span data-stu-id="5beeb-102">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>
<span data-ttu-id="5beeb-103">Web サービスとして発行したオーケストレーションから SOAP 例外を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="5beeb-103">You can return a SOAP exception from an orchestration that you have published as a Web service.</span></span> <span data-ttu-id="5beeb-104">SOAP ポートにエラー メッセージを追加し、応答ではなく、エラー メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5beeb-104">You add a fault message to your SOAP port and send the fault message instead of the response.</span></span>  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a><span data-ttu-id="5beeb-105">Web サービスとして公開されたオーケストレーションから SOAP 例外をスローするには</span><span class="sxs-lookup"><span data-stu-id="5beeb-105">To throw a SOAP exception from an orchestration published as a Web service</span></span>  
  
1. <span data-ttu-id="5beeb-106">SOAP ポートの種類には、エラー メッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="5beeb-106">Add a fault message to the SOAP port type.</span></span> <span data-ttu-id="5beeb-107">エラー メッセージのメッセージの種類には、任意の XML スキーマ (XSD) 準拠のスキーマまたは単純型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5beeb-107">The message type for the fault message can be any XML Schema (XSD) compliant schema or simple type.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5beeb-108">として文字列を返す、 **SoapException**エラー情報と共にエラー メッセージの種類として単純型の文字列を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5beeb-108">To return a string as a **SoapException** with error information, you can use the simple type string as the fault message type.</span></span>  
  
2. <span data-ttu-id="5beeb-109">オーケストレーションでは、エラー メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="5beeb-109">In your orchestration, create the fault message.</span></span>  
  
3. <span data-ttu-id="5beeb-110">使用して、**送信**図形をエラー メッセージに対応する SOAP ポートでのエラー操作にリンクします。</span><span class="sxs-lookup"><span data-stu-id="5beeb-110">Use the **Send** shape to link to the fault operation in the SOAP port that corresponds to the fault message.</span></span> <span data-ttu-id="5beeb-111">SOAP 例外は、返されたエラー メッセージをラップします。</span><span class="sxs-lookup"><span data-stu-id="5beeb-111">A SOAP exception wraps the returned fault message.</span></span>  
  
   <span data-ttu-id="5beeb-112">オーケストレーションがエラーを返さない場合を使用して、さまざまな**送信**図形を通常の応答の操作を使用して標準の SOAP 応答メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5beeb-112">If your orchestration does not return an error, use a different **Send** shape to send the standard SOAP response message using the usual response operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5beeb-113">参照</span><span class="sxs-lookup"><span data-stu-id="5beeb-113">See Also</span></span>  
 <span data-ttu-id="5beeb-114">[エラー メッセージ](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="5beeb-114">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="5beeb-115">Web サービスとしてのオーケストレーションの公開</span><span class="sxs-lookup"><span data-stu-id="5beeb-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)
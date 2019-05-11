---
title: TIBCO EMS メッセージ コンテキスト プロパティの使用 |Microsoft Docs
description: BizTalk Server オーケストレーションで TIBCO Enterprise Message System のメッセージ記述子フィールドを使用します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c4c095969483905cf30403e4831e4f2df8296b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394572"
---
# <a name="message-context-properties-in-tibco-ems"></a><span data-ttu-id="97a7a-103">TIBCO EMS のメッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="97a7a-103">Message Context Properties in TIBCO EMS</span></span>

## <a name="tibcoemspropertiesdll"></a><span data-ttu-id="97a7a-104">TibcoEMSProperties.dll</span><span class="sxs-lookup"><span data-stu-id="97a7a-104">TibcoEMSProperties.dll</span></span>
<span data-ttu-id="97a7a-105">TIBCO Enterprise Message System のメッセージ記述子フィールドは、BizTalk Server オーケストレーションからアクセスするへの参照を追加する必要があります**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="97a7a-105">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="97a7a-106">このアセンブリにある **\<TIBCO EMS_Adapter_installation_directory\>\bin**します。</span><span class="sxs-lookup"><span data-stu-id="97a7a-106">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory\>\bin**.</span></span> <span data-ttu-id="97a7a-107">この TIBCO EMS プロパティ スキーマを参照すると、追加のコンテキスト プロパティは、さまざまな BizTalk Server 開発ツール (たとえば、オーケストレーション デザイナーでのメッセージの割り当て図形) でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="97a7a-107">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="access-context-properties"></a><span data-ttu-id="97a7a-108">コンテキスト プロパティへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="97a7a-108">Access context Properties</span></span>  
 <span data-ttu-id="97a7a-109">コンテキスト プロパティにアクセスするには、で指定した使用可能なコンテキスト プロパティの 1 つ、TIBCO EMS 名前空間。</span><span class="sxs-lookup"><span data-stu-id="97a7a-109">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="97a7a-110">BizTalk Adapter for TIBCO EMS にバインドのポートから受信したメッセージのコンテキスト プロパティを読み取りするには、式の中で、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="97a7a-110">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="97a7a-111">詳細については、次を参照してください。 [TIBCO Enterprise Message Service メッセージ記述子プロパティ](../core/tibco-enterprise-message-service-message-descriptor-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="97a7a-111">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="97a7a-112">BizTalk Server で、メッセージは変更できません。</span><span class="sxs-lookup"><span data-stu-id="97a7a-112">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="97a7a-113">そのため、するメッセージ コンテキスト プロパティの値を割り当てるには、新しいメッセージを作成、(場合によっては、既存のメッセージの割り当て)、メッセージの内容を設定して、必要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="97a7a-113">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="97a7a-114">に TIBCO EMS 用 BizTalk アダプターにバインドされている送信ポートに送信されたメッセージを TIBCO EMS のコンテキスト プロパティを割り当てるに、メッセージ代入演算子を使用し、TIBCO EMS 名前空間で使用できるプロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="97a7a-114">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="97a7a-115">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="97a7a-115">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a><span data-ttu-id="97a7a-116">次のステップ</span><span class="sxs-lookup"><span data-stu-id="97a7a-116">Next steps</span></span>
-   [<span data-ttu-id="97a7a-117">TIBCO EMS メッセージ記述子のプロパティと値</span><span class="sxs-lookup"><span data-stu-id="97a7a-117">TIBCO EMS Message Descriptor properties & values</span></span>](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [<span data-ttu-id="97a7a-118">チュートリアル: メッセージ コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="97a7a-118">Tutorial: Use Message Context Properties</span></span>](../core/tutorial-using-message-context-properties.md)
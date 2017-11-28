---
title: "メッセージ コンテキスト プロパティを BizTalk Server で |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, accessing
- message context properties, BizTalk Server
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e92e458ec6927ab8e1bc6082cd9a71ee3e4387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-in-biztalk-server"></a><span data-ttu-id="d3dbb-102">BizTalk Server におけるメッセージのコンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3dbb-102">Message Context Properties in BizTalk Server</span></span>
<span data-ttu-id="d3dbb-103">BizTalk Server オーケストレーションから TIBCO Enterprise Message System のメッセージ記述子フィールドにアクセスするへの参照を追加する必要があります**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-103">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="d3dbb-104">このアセンブリにある **\<TIBCO EMS_Adapter_installation_directory > \bin**です。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-104">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory>\bin**.</span></span> <span data-ttu-id="d3dbb-105">この TIBCO EMS のプロパティ スキーマにアクセスすると、さらに多くのコンテキスト プロパティに、さまざまな BizTalk Server 開発ツールからアクセスできるようになります (オーケストレーション デザイナのメッセージ割り当て図形など)。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-105">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="accessing-context-properties"></a><span data-ttu-id="d3dbb-106">コンテキスト プロパティへのアクセス</span><span class="sxs-lookup"><span data-stu-id="d3dbb-106">Accessing Context Properties</span></span>  
 <span data-ttu-id="d3dbb-107">コンテキスト プロパティにアクセスするには、TIBCO EMS 名前空間の使用できるプロパティのうちいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-107">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="d3dbb-108">TIBCO EMS 用の BizTalk アダプタにバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-108">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="d3dbb-109">詳細については、次を参照してください。 [TIBCO Enterprise Message Service メッセージ記述子プロパティ](../core/tibco-enterprise-message-service-message-descriptor-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-109">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="d3dbb-110">BizTalk Server では、メッセージを変更できません。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-110">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="d3dbb-111">このため、メッセージのコンテキスト プロパティに値を割り当てるには、新しいメッセージを作成し、メッセージのコンテキストを設定して (既存のメッセージを割り当てるなど)、必要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-111">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="d3dbb-112">TIBCO EMS の BizTalk アダプターにバインドされている送信ポートに送信メッセージに TIBCO EMS のコンテキスト プロパティを割り当てる、メッセージ代入演算子を使用し、TIBCO EMS 名前空間に使用できるコンテキスト プロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-112">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="d3dbb-113">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3dbb-113">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3dbb-114">参照</span><span class="sxs-lookup"><span data-stu-id="d3dbb-114">See Also</span></span>  
 [<span data-ttu-id="d3dbb-115">メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3dbb-115">Message Context Properties</span></span>](../core/message-context-properties2.md)
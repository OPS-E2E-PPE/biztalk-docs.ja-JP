---
title: "TIBCO EMS メッセージ コンテキスト プロパティを使用して |Microsoft ドキュメント"
description: "BizTalk Server オーケストレーションで TIBCO Enterprise Message System のメッセージ記述子フィールドを使用します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4f0d8c606724cec9c85551251cb003aa8a7e34
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="message-context-properties-in-tibco-ems"></a><span data-ttu-id="361ce-103">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="361ce-103">Message Context Properties in TIBCO EMS</span></span>

## <a name="tibcoemspropertiesdll"></a><span data-ttu-id="361ce-104">TibcoEMSProperties.dll</span><span class="sxs-lookup"><span data-stu-id="361ce-104">TibcoEMSProperties.dll</span></span>
<span data-ttu-id="361ce-105">BizTalk Server オーケストレーションから TIBCO Enterprise Message System のメッセージ記述子フィールドにアクセスするへの参照を追加する必要があります**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="361ce-105">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="361ce-106">このアセンブリにある **\<TIBCO EMS_Adapter_installation_directory > \bin**です。</span><span class="sxs-lookup"><span data-stu-id="361ce-106">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory>\bin**.</span></span> <span data-ttu-id="361ce-107">この TIBCO EMS のプロパティ スキーマにアクセスすると、さらに多くのコンテキスト プロパティに、さまざまな BizTalk Server 開発ツールからアクセスできるようになります (オーケストレーション デザイナのメッセージ割り当て図形など)。</span><span class="sxs-lookup"><span data-stu-id="361ce-107">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="access-context-properties"></a><span data-ttu-id="361ce-108">コンテキスト プロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="361ce-108">Access context Properties</span></span>  
 <span data-ttu-id="361ce-109">コンテキスト プロパティにアクセスするには、TIBCO EMS 名前空間の使用できるプロパティのうちいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="361ce-109">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="361ce-110">TIBCO EMS 用の BizTalk アダプタにバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="361ce-110">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="361ce-111">詳細については、次を参照してください。 [TIBCO Enterprise Message Service メッセージ記述子プロパティ](../core/tibco-enterprise-message-service-message-descriptor-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="361ce-111">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="361ce-112">BizTalk Server では、メッセージを変更できません。</span><span class="sxs-lookup"><span data-stu-id="361ce-112">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="361ce-113">このため、メッセージのコンテキスト プロパティに値を割り当てるには、新しいメッセージを作成し、メッセージのコンテキストを設定して (既存のメッセージを割り当てるなど)、必要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="361ce-113">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="361ce-114">TIBCO EMS の BizTalk アダプターにバインドされている送信ポートに送信メッセージに TIBCO EMS のコンテキスト プロパティを割り当てる、メッセージ代入演算子を使用し、TIBCO EMS 名前空間に使用できるコンテキスト プロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="361ce-114">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="361ce-115">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="361ce-115">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a><span data-ttu-id="361ce-116">次の手順</span><span class="sxs-lookup"><span data-stu-id="361ce-116">Next steps</span></span>
-   [<span data-ttu-id="361ce-117">TIBCO EMS メッセージ記述子のプロパティと値</span><span class="sxs-lookup"><span data-stu-id="361ce-117">TIBCO EMS Message Descriptor properties & values</span></span>](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [<span data-ttu-id="361ce-118">チュートリアル: メッセージ コンテキストのプロパティの使用</span><span class="sxs-lookup"><span data-stu-id="361ce-118">Tutorial: Use Message Context Properties</span></span>](../core/tutorial-using-message-context-properties.md)
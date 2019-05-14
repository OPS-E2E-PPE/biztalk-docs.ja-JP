---
title: メッセージ コンテキスト プロパティ Values1 を割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e76c62-3110-482c-8083-84d411e6f475
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e66d88a2e12bb0e2672c04df06df711746c5efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387191"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="531be-102">メッセージ コンテキスト プロパティの値を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="531be-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="531be-103">を BizTalk オーケストレーションから JD Edwards EnterpriseOne アダプター接続セッションを管理するには、プロジェクトの Microsoft.BizTalk.Adapters.JDEProperties.dll に参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="531be-103">To manage the JD Edwards EnterpriseOne Adapter connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="531be-104">このアセンブリは %systemdrive%\program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin にあります。</span><span class="sxs-lookup"><span data-stu-id="531be-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="531be-105">このプロパティ スキーマを参照すると後、は、追加のコンテキスト プロパティをさまざまな BizTalk 開発ツール、たとえば、メッセージの割り当て図形をオーケストレーション デザイナー内でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="531be-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="531be-106">コンテキスト プロパティにアクセスするには、JD Edwards EnterpriseOne 名前空間内で使用できるプロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="531be-106">To access a context property, you specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span> <span data-ttu-id="531be-107">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取りは、メッセージ (JDE の構文を使用します。プロパティの場合)、式で。</span><span class="sxs-lookup"><span data-stu-id="531be-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="531be-108">プロパティの一覧については、JD Edwards EnterpriseOne アダプター セッション管理を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531be-108">Refer to JD Edwards EnterpriseOne Adapter Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="531be-109">BizTalk メッセージは変更できません。</span><span class="sxs-lookup"><span data-stu-id="531be-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-context-property-value"></a><span data-ttu-id="531be-110">コンテキスト プロパティの値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="531be-110">To assign context property value</span></span>  
  
1. <span data-ttu-id="531be-111">新しいメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="531be-111">Create a new message.</span></span>  
  
2. <span data-ttu-id="531be-112">コンテンツの設定、メッセージなどの既存のメッセージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="531be-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3. <span data-ttu-id="531be-113">プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="531be-113">Set the properties.</span></span>  
  
   <span data-ttu-id="531be-114">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされている送信ポートに送信メッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="531be-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the message assignment operator.</span></span> <span data-ttu-id="531be-115">JD Edwards EnterpriseOne 名前空間内で使用できるプロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="531be-115">Then specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span>  
  
   <span data-ttu-id="531be-116">次の構文 `Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="531be-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531be-117">参照</span><span class="sxs-lookup"><span data-stu-id="531be-117">See Also</span></span>  
 <span data-ttu-id="531be-118">[メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties1.md) </span><span class="sxs-lookup"><span data-stu-id="531be-118">[Using Message Context Properties](../core/using-message-context-properties1.md) </span></span>  
 <span data-ttu-id="531be-119">[セッション管理について](../core/about-session-management2.md) </span><span class="sxs-lookup"><span data-stu-id="531be-119">[About Session Management](../core/about-session-management2.md) </span></span>  
 [<span data-ttu-id="531be-120">チュートリアル: BizTalk Adapter for JD Edwards EnterpriseOne の使用</span><span class="sxs-lookup"><span data-stu-id="531be-120">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)
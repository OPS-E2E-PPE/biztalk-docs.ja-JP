---
title: メッセージ コンテキスト プロパティ Values2 を割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083fa3e8d6474e0f369cc1c66210ac39f4e1d56e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342700"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="80f90-102">メッセージ コンテキスト プロパティの値を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="80f90-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="80f90-103">を BizTalk オーケストレーションから JD Edwards OneWorld 接続セッションを管理するには、プロジェクトの Microsoft.BizTalk.Adapters.JDEProperties.dll に参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80f90-103">To manage the JD Edwards OneWorld connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="80f90-104">このアセンブリは %systemdrive%\program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin にあります。</span><span class="sxs-lookup"><span data-stu-id="80f90-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="80f90-105">このプロパティ スキーマを参照すると後、は、追加のコンテキスト プロパティをさまざまな BizTalk 開発ツール、たとえば、メッセージの割り当て図形をオーケストレーション デザイナー内でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="80f90-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="80f90-106">コンテキスト プロパティにアクセスするには、JD Edwards OneWorld 名前空間内で使用できるプロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f90-106">To access a context property, you specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span> <span data-ttu-id="80f90-107">Microsoft BizTalk Adapter for JD Edwards OneWorld にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取りは、メッセージ (JDE の構文を使用します。プロパティの場合)、式で。</span><span class="sxs-lookup"><span data-stu-id="80f90-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="80f90-108">プロパティの一覧については、JD Edwards OneWorld セッション管理を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f90-108">Refer to JD Edwards OneWorld Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="80f90-109">BizTalk メッセージは変更できません。</span><span class="sxs-lookup"><span data-stu-id="80f90-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-a-message-context-property-value"></a><span data-ttu-id="80f90-110">メッセージ コンテキスト プロパティの値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="80f90-110">To assign a message context property value</span></span>  
  
1. <span data-ttu-id="80f90-111">新しいメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="80f90-111">Create a new message.</span></span>  
  
2. <span data-ttu-id="80f90-112">コンテンツの設定、メッセージなどの既存のメッセージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80f90-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3. <span data-ttu-id="80f90-113">プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="80f90-113">Set the properties.</span></span>  
  
   <span data-ttu-id="80f90-114">Microsoft BizTalk Adapter for JD Edwards OneWorld にバインドされている送信ポートに送信メッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="80f90-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the message assignment operator.</span></span> <span data-ttu-id="80f90-115">次に、JD Edwards OneWorld 名前空間内で使用できるプロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="80f90-115">Then, specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span>  
  
   <span data-ttu-id="80f90-116">次の構文 `Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="80f90-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f90-117">参照</span><span class="sxs-lookup"><span data-stu-id="80f90-117">See Also</span></span>  
 <span data-ttu-id="80f90-118">[メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="80f90-118">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="80f90-119">[セッション管理について](../core/about-session-management1.md) </span><span class="sxs-lookup"><span data-stu-id="80f90-119">[About Session Management](../core/about-session-management1.md) </span></span>  
 [<span data-ttu-id="80f90-120">チュートリアル: BizTalk Adapter for JD Edwards OneWorld の使用</span><span class="sxs-lookup"><span data-stu-id="80f90-120">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)
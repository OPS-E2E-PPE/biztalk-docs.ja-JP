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
ms.openlocfilehash: 4f9f5a42e208d81f8898ce85592402f675d1b361
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979743"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="424bb-102">メッセージ コンテキスト プロパティの値を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="424bb-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="424bb-103">BizTalk オーケストレーションから JD Edwards EnterpriseOne アダプター接続セッションを管理するには、Microsoft.BizTalk.Adapters.JDEProperties.dll への参照をプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="424bb-103">To manage the JD Edwards EnterpriseOne Adapter connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="424bb-104">このアセンブリは、%SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin に配置されています。</span><span class="sxs-lookup"><span data-stu-id="424bb-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="424bb-105">このプロパティ スキーマを参照すると、オーケストレーション デザイナのメッセージの割り当て図形など、さまざまな BizTalk 開発ツールで、追加のコンテキスト プロパティにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="424bb-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="424bb-106">コンテキスト プロパティにアクセスするには、JD Edwards EnterpriseOne 名前空間で使用できるコンテキスト プロパティのうちいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="424bb-106">To access a context property, you specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span> <span data-ttu-id="424bb-107">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で構文 Message(JDE.Property) を使用します。</span><span class="sxs-lookup"><span data-stu-id="424bb-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="424bb-108">プロパティの一覧については、JD Edwards EnterpriseOne アダプター セッション管理に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="424bb-108">Refer to JD Edwards EnterpriseOne Adapter Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="424bb-109">BizTalk では、メッセージを変更できません。</span><span class="sxs-lookup"><span data-stu-id="424bb-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-context-property-value"></a><span data-ttu-id="424bb-110">コンテキスト プロパティ値を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="424bb-110">To assign context property value</span></span>  
  
1. <span data-ttu-id="424bb-111">新しいメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="424bb-111">Create a new message.</span></span>  
  
2. <span data-ttu-id="424bb-112">メッセージのコンテンツを設定します (既存のメッセージを割り当てるなど)。</span><span class="sxs-lookup"><span data-stu-id="424bb-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3. <span data-ttu-id="424bb-113">プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="424bb-113">Set the properties.</span></span>  
  
   <span data-ttu-id="424bb-114">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされた送信ポートに送信するメッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="424bb-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the message assignment operator.</span></span> <span data-ttu-id="424bb-115">次に、JD Edwards EnterpriseOne 名前空間の使用可能ないずれかのコンテキスト プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="424bb-115">Then specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span>  
  
   <span data-ttu-id="424bb-116">次の構文 `Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="424bb-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="424bb-117">参照</span><span class="sxs-lookup"><span data-stu-id="424bb-117">See Also</span></span>  
 <span data-ttu-id="424bb-118">[メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties1.md) </span><span class="sxs-lookup"><span data-stu-id="424bb-118">[Using Message Context Properties](../core/using-message-context-properties1.md) </span></span>  
 <span data-ttu-id="424bb-119">[セッション管理について](../core/about-session-management2.md) </span><span class="sxs-lookup"><span data-stu-id="424bb-119">[About Session Management](../core/about-session-management2.md) </span></span>  
 [<span data-ttu-id="424bb-120">チュートリアル: BizTalk Adapter for JD Edwards EnterpriseOne の使用</span><span class="sxs-lookup"><span data-stu-id="424bb-120">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)
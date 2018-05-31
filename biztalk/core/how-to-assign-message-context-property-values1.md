---
title: メッセージ コンテキスト プロパティ Values1 に割り当てる方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 39bb2a4c6520c1ff3a21889e7508bb2cf417b817
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247306"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="09388-102">メッセージ コンテキスト プロパティの値を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="09388-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="09388-103">BizTalk オーケストレーションから JD Edwards EnterpriseOne アダプター接続セッションを管理するには、Microsoft.BizTalk.Adapters.JDEProperties.dll への参照をプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09388-103">To manage the JD Edwards EnterpriseOne Adapter connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="09388-104">このアセンブリは、%SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin に配置されています。</span><span class="sxs-lookup"><span data-stu-id="09388-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="09388-105">このプロパティ スキーマを参照すると、オーケストレーション デザイナのメッセージの割り当て図形など、さまざまな BizTalk 開発ツールで、追加のコンテキスト プロパティにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="09388-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="09388-106">コンテキスト プロパティにアクセスするには、JD Edwards EnterpriseOne 名前空間で使用できるコンテキスト プロパティのうちいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="09388-106">To access a context property, you specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span> <span data-ttu-id="09388-107">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で構文 Message(JDE.Property) を使用します。</span><span class="sxs-lookup"><span data-stu-id="09388-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="09388-108">プロパティの一覧については、JD Edwards EnterpriseOne アダプター セッション管理に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09388-108">Refer to JD Edwards EnterpriseOne Adapter Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="09388-109">BizTalk では、メッセージを変更できません。</span><span class="sxs-lookup"><span data-stu-id="09388-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-context-property-value"></a><span data-ttu-id="09388-110">コンテキスト プロパティ値を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="09388-110">To assign context property value</span></span>  
  
1.  <span data-ttu-id="09388-111">新しいメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="09388-111">Create a new message.</span></span>  
  
2.  <span data-ttu-id="09388-112">メッセージのコンテンツを設定します (既存のメッセージを割り当てるなど)。</span><span class="sxs-lookup"><span data-stu-id="09388-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3.  <span data-ttu-id="09388-113">プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09388-113">Set the properties.</span></span>  
  
 <span data-ttu-id="09388-114">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne にバインドされた送信ポートに送信するメッセージにコンテキスト プロパティを割り当てるには、メッセージ代入演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="09388-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the message assignment operator.</span></span> <span data-ttu-id="09388-115">次に、JD Edwards EnterpriseOne 名前空間の使用可能ないずれかのコンテキスト プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="09388-115">Then specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span>  
  
 <span data-ttu-id="09388-116">構文です。`Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="09388-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09388-117">参照</span><span class="sxs-lookup"><span data-stu-id="09388-117">See Also</span></span>  
 <span data-ttu-id="09388-118">[メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties1.md) </span><span class="sxs-lookup"><span data-stu-id="09388-118">[Using Message Context Properties](../core/using-message-context-properties1.md) </span></span>  
 <span data-ttu-id="09388-119">[セッション管理について](../core/about-session-management2.md) </span><span class="sxs-lookup"><span data-stu-id="09388-119">[About Session Management](../core/about-session-management2.md) </span></span>  
 [<span data-ttu-id="09388-120">チュートリアル: BizTalk アダプターを使用して JD Edwards EnterpriseOne の</span><span class="sxs-lookup"><span data-stu-id="09388-120">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)
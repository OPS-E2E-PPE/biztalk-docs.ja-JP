---
title: スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e3197dee20a222be35aa2e72dc4ac5e04208da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389881"
---
# <a name="creating-schemas"></a><span data-ttu-id="917ba-102">スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="917ba-102">Creating Schemas</span></span>
<span data-ttu-id="917ba-103">BizTalk エディターを使用して、2 つの種類のスキーマを作成することができます。 メッセージのスキーマとプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="917ba-103">You can use BizTalk Editor to create two types of schemas: message schemas and property schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="917ba-104">いくつかの種類のメッセージ スキーマ、XML メッセージ スキーマやフラット ファイル メッセージ スキーマをエンベロープ スキーマなどがあります。</span><span class="sxs-lookup"><span data-stu-id="917ba-104">There are several types of message schemas, including XML message schemas, flat file message schemas, and envelope schemas.</span></span>  
  
 <span data-ttu-id="917ba-105">メッセージ スキーマでは、構造を定義しに送信し、取引先パートナーまたはアプリケーションから受信するメッセージの内容を制限します。</span><span class="sxs-lookup"><span data-stu-id="917ba-105">Message schemas define the structure and constrain the content of messages that you expect to send to, and receive from, your trading partners or applications.</span></span> <span data-ttu-id="917ba-106">メッセージ スキーマは、最も一般的な種類の Microsoft で使用するスキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="917ba-106">Message schemas are the most common types of schemas that you will use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="917ba-107">ビジネス ドキュメントと、それを格納するために使用するエンベロープの両方の XML メッセージ スキーマを作成し、フラット ファイル メッセージ スキーマ、ヘッダー、ボディ、およびトレーラーのスキーマを含むフラット ファイル拡張子 BizTalk エディターを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="917ba-107">can create XML message schemas for both business documents and the envelopes used to contain them, and through the use of the Flat File Extension to BizTalk Editor, it can create flat file message schemas, including schemas for headers, bodies and trailers.</span></span>  
  
 <span data-ttu-id="917ba-108">プロパティ スキーマは、特殊な種類のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="917ba-108">Property schemas are a special type of schema.</span></span> <span data-ttu-id="917ba-109">プロパティ スキーマは、フィールドやレコード データは、インスタンス メッセージ内にメッセージ コンテキストと呼ばれるものから昇格を検証テンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="917ba-109">Property schemas provide a validation template for field and/or record data that is promoted from within an instance message into what is known as the message context.</span></span> <span data-ttu-id="917ba-110">プロパティ スキーマでは、実行時に昇格するデータの正式な厳密に型指定された定義を指定します。</span><span class="sxs-lookup"><span data-stu-id="917ba-110">The purpose of property schemas is to provide a formal, strongly typed definition of the data to be promoted at run time.</span></span>  
  
 <span data-ttu-id="917ba-111">プロパティの昇格の重要な情報を取得するための一元的なメカニズムを提供します。 定義したからインスタンス メッセージより簡単にアクセスできるようにする BizTalk Server コンポーネントをメッセージの処理 BizTalk に渡されますサーバー。</span><span class="sxs-lookup"><span data-stu-id="917ba-111">Property promotion provides a centralized mechanism for pulling key pieces of information, defined by you, from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span> <span data-ttu-id="917ba-112">昇格させたプロパティの 1 つの一般的な用途は、メッセージを処理するため正しくルーティングできるように、サブスクリプションにメッセージ インスタンスと一致します。</span><span class="sxs-lookup"><span data-stu-id="917ba-112">One common use of promoted properties is in matching a message instance to a subscription, allowing the message to be properly routed for processing.</span></span>  
  
 <span data-ttu-id="917ba-113">このセクションでは、さまざまな種類の BizTalk Server 内のスキーマを作成する方法について説明し、関連項目に関連する複数の種類のスキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="917ba-113">This section describes the ways in which you can create different types of schemas within BizTalk Server, and presents related subjects that pertain to multiple types of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="917ba-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="917ba-114">In This Section</span></span>  
  
-   [<span data-ttu-id="917ba-115">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="917ba-115">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)  
  
-   [<span data-ttu-id="917ba-116">スキーマ内のノードの管理</span><span class="sxs-lookup"><span data-stu-id="917ba-116">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)  
  
-   [<span data-ttu-id="917ba-117">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="917ba-117">Promoting Properties</span></span>](../core/promoting-properties.md)
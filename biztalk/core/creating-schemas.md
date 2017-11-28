---
title: "スキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac019276923467fe2d95f5a0a0b4a7b53513e9c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-schemas"></a><span data-ttu-id="48f11-102">スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="48f11-102">Creating Schemas</span></span>
<span data-ttu-id="48f11-103">BizTalk エディターを使用して、2 つの種類のスキーマを作成することができます。 メッセージのスキーマとプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="48f11-103">You can use BizTalk Editor to create two types of schemas: message schemas and property schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48f11-104">メッセージ スキーマにはいくつかの種類 (XML メッセージ スキーマ、フラット ファイル メッセージ スキーマ、およびエンベロープ スキーマ) があります。</span><span class="sxs-lookup"><span data-stu-id="48f11-104">There are several types of message schemas, including XML message schemas, flat file message schemas, and envelope schemas.</span></span>  
  
 <span data-ttu-id="48f11-105">メッセージ スキーマでは、構造を定義して、取引先やアプリケーションとの送信および受信を行うメッセージの内容を制限します。</span><span class="sxs-lookup"><span data-stu-id="48f11-105">Message schemas define the structure and constrain the content of messages that you expect to send to, and receive from, your trading partners or applications.</span></span> <span data-ttu-id="48f11-106">メッセージ スキーマは、最も一般的な種類の Microsoft による使用するスキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="48f11-106">Message schemas are the most common types of schemas that you will use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="48f11-107">ビジネス ドキュメントと、それを格納するために使用するエンベロープの両方の XML メッセージ スキーマを作成し、フラット ファイル メッセージ スキーマ、ヘッダー、ボディ、およびトレーラーのスキーマを含むフラット ファイル拡張子 BizTalk エディターを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="48f11-107"> can create XML message schemas for both business documents and the envelopes used to contain them, and through the use of the Flat File Extension to BizTalk Editor, it can create flat file message schemas, including schemas for headers, bodies and trailers.</span></span>  
  
 <span data-ttu-id="48f11-108">プロパティ スキーマは、特殊なスキーマです。</span><span class="sxs-lookup"><span data-stu-id="48f11-108">Property schemas are a special type of schema.</span></span> <span data-ttu-id="48f11-109">プロパティ スキーマは、インスタンス メッセージからメッセージ コンテキストに昇格されるフィールドおよびレコードのデータに使用する検証テンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="48f11-109">Property schemas provide a validation template for field and/or record data that is promoted from within an instance message into what is known as the message context.</span></span> <span data-ttu-id="48f11-110">プロパティ スキーマは、実行時に昇格される厳密に型指定された正式なデータを提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="48f11-110">The purpose of property schemas is to provide a formal, strongly typed definition of the data to be promoted at run time.</span></span>  
  
 <span data-ttu-id="48f11-111">プロパティの昇格の重要な情報をプルするための集中管理メカニズムを提供、定義したからインスタンス メッセージより簡単にアクセスできるようにする BizTalk Server コンポーネントを内でメッセージの処理を BizTalk を通過するときサーバー。</span><span class="sxs-lookup"><span data-stu-id="48f11-111">Property promotion provides a centralized mechanism for pulling key pieces of information, defined by you, from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span> <span data-ttu-id="48f11-112">昇格させたプロパティの一般的な使用方法は、メッセージ インスタンスとサブスクリプションを照合することです。これにより、メッセージを正しくルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="48f11-112">One common use of promoted properties is in matching a message instance to a subscription, allowing the message to be properly routed for processing.</span></span>  
  
 <span data-ttu-id="48f11-113">このセクションでは、BizTalk Server のさまざまなスキーマを作成する方法について説明し、複数の種類のスキーマの関連項目を示します。</span><span class="sxs-lookup"><span data-stu-id="48f11-113">This section describes the ways in which you can create different types of schemas within BizTalk Server, and presents related subjects that pertain to multiple types of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48f11-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="48f11-114">In This Section</span></span>  
  
-   [<span data-ttu-id="48f11-115">プロジェクト内のスキーマを管理します。</span><span class="sxs-lookup"><span data-stu-id="48f11-115">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)  
  
-   [<span data-ttu-id="48f11-116">スキーマ内のノードを管理します。</span><span class="sxs-lookup"><span data-stu-id="48f11-116">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)  
  
-   [<span data-ttu-id="48f11-117">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="48f11-117">Promoting Properties</span></span>](../core/promoting-properties.md)
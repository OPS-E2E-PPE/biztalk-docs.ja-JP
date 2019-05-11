---
title: インスタンス メッセージについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de7fc3d3-57a7-4df9-b981-127e21941e22
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ccd2e6cbaca7a592c54fd2d36941ac1c004440c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362353"
---
# <a name="about-instance-messages"></a><span data-ttu-id="2b349-102">インスタンス メッセージについて</span><span class="sxs-lookup"><span data-stu-id="2b349-102">About Instance Messages</span></span>
<span data-ttu-id="2b349-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、インスタンス メッセージの送受信を行います。通常、各インスタンス メッセージは、注文書などの 1 つ以上のビジネス ドキュメントを表します。</span><span class="sxs-lookup"><span data-stu-id="2b349-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends and receives instance messages, each of which typically represents one or more business documents such as a purchase order.</span></span> <span data-ttu-id="2b349-104">インスタンス メッセージは、1 つ以上のスキーマで定義されるメッセージ構造のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="2b349-104">An instance message is an instance of a message structure defined by one or more schemas.</span></span> <span data-ttu-id="2b349-105">スキーマまたはスキーマ セットは、有効なインスタンス メッセージを構成するための情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b349-105">A schema, or a set of schemas being used together, defines what constitutes a valid instance message.</span></span> <span data-ttu-id="2b349-106">たとえば、注文書を定義して、複数のレコード (ShipTo レコード、BillTo レコード、Item レコードなど) を格納することがあります。</span><span class="sxs-lookup"><span data-stu-id="2b349-106">For example, a purchase order might be defined to have several records within it, such as a ShipTo record, a BillTo record, an Items record, and so on.</span></span> <span data-ttu-id="2b349-107">これらの各レコードを定義して、固有のサブレコードやフィールドを格納できます。</span><span class="sxs-lookup"><span data-stu-id="2b349-107">Each of these records can be defined to contain their own subrecords and fields.</span></span> <span data-ttu-id="2b349-108">対応するスキーマでは、これらのレコードやフィールドに関する情報を定義します。また、対応するインスタンス メッセージは、スキーマに基づいて構成された注文書のデータを含む実際の注文書を格納します。</span><span class="sxs-lookup"><span data-stu-id="2b349-108">The corresponding schema defines the potential contents of these records and fields and the corresponding instance messages contain actual purchase orders that contain purchase order data structured according to the schema.</span></span>  
  
 <span data-ttu-id="2b349-109">BizTalk Server は、拡張可能なさまざまな形式でインスタンス メッセージの送受信を行うことができます。特に XML 形式は重要な形式です。すべてのメッセージ形式は、内部処理によって XML 形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2b349-109">BizTalk Server can send and receive instance messages in an extensible variety of formats although one format, XML, has special significance as the format into which all message formats are translated for internal processing.</span></span> <span data-ttu-id="2b349-110">XML ドキュメントでは、階層的に配置されている開始タグや終了タグに関する定義のセットを使用して、メッセージ内のデータの編成、およびデータ項目の終了場所と別のデータ項目の開始場所を判別します。</span><span class="sxs-lookup"><span data-stu-id="2b349-110">A particular XML document uses a well-defined set of starting and ending tags, arranged hierarchically, to organize the data within the message and determine where one data item ends and another begins.</span></span> <span data-ttu-id="2b349-111">インスタンス メッセージに対応する XML スキーマでは、あるタグ内で使用可能なタグとその順序を定義します。これにより、メッセージの構造が管理されます。</span><span class="sxs-lookup"><span data-stu-id="2b349-111">One or more corresponding XML schemas define which tags are allowed within other tags, in what order, thereby governing the structure of conforming messages.</span></span>  
  
 <span data-ttu-id="2b349-112">フラット ファイル形式という種類の形式は、レガシ システムで一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b349-112">Another broad category of formats, known as flat file formats, are commonly used by legacy systems.</span></span> <span data-ttu-id="2b349-113">この形式では、タブなどの区切り記号と固定長のフィールドを組み合わせて、データ項目の終了場所と別のデータ項目の開始場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="2b349-113">These formats use some combination of delimiters (such as tabs) and fixed length fields to determine where one data item ends and another begins.</span></span>  
  
 <span data-ttu-id="2b349-114">このセクションでは、BizTalk Server で一般的に処理されるこれらの 2 種類のメッセージの構造の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b349-114">This section provides a high-level overview of the structure of these two types of messages that are commonly handled by BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b349-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2b349-115">In This Section</span></span>  
  
-   [<span data-ttu-id="2b349-116">XML メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="2b349-116">Structure of an XML Message</span></span>](../core/structure-of-an-xml-message.md)  
  
-   [<span data-ttu-id="2b349-117">フラット ファイル メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="2b349-117">Structure of a Flat File Message</span></span>](../core/structure-of-a-flat-file-message.md)
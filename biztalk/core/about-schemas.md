---
title: "スキーマに関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ec2b79c-7cfe-4b00-bcff-dfad3944c83b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a452675cb11b13ae83f940ce10b09c72a622dc8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-schemas"></a><span data-ttu-id="07cb8-102">スキーマについて</span><span class="sxs-lookup"><span data-stu-id="07cb8-102">About Schemas</span></span>
<span data-ttu-id="07cb8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、処理されるすべてのメッセージの構造を XML スキーマ定義 (XSD) 言語で定義します。メッセージ構造のこのような定義をスキーマと呼びます。</span><span class="sxs-lookup"><span data-stu-id="07cb8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the XML Schema definition (XSD) language to define the structure of all messages that it processes, and refers to these definitions of message structure as schemas.</span></span> <span data-ttu-id="07cb8-104">ほとんど例外なく、構造化されたメッセージは、アプリケーションの中核を成すものです。</span><span class="sxs-lookup"><span data-stu-id="07cb8-104">With few exceptions, structured messages are the core of any application.</span></span> <span data-ttu-id="07cb8-105">これらの構造化されたメッセージは、大小さまざまな形式になります。また、多種多様なバックエンド システムおよびデータ ストアを対象とします。</span><span class="sxs-lookup"><span data-stu-id="07cb8-105">These structured messages can take any form, large or small, and target a wide array of back-end systems and data stores.</span></span> <span data-ttu-id="07cb8-106">構造化されたメッセージを頻繁に作成して使用するシステムは、さまざまな形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="07cb8-106">Systems that create and consume the structured messages frequently use different formats.</span></span> <span data-ttu-id="07cb8-107">構造化されたメッセージの最も一般的な形式は、XML とフラット ファイルです。</span><span class="sxs-lookup"><span data-stu-id="07cb8-107">Two of the most common formats for structured messages are XML and flat files.</span></span>  
  
 <span data-ttu-id="07cb8-108">BizTalk エディターを使用すると、メッセージ スキーマを定義して特定のメッセージがスキーマに準拠するかどうかを検証する処理が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="07cb8-108">BizTalk Editor is designed to simplify the process of defining a message schema and validating whether a particular message conforms to that schema.</span></span> <span data-ttu-id="07cb8-109">スキーマの定義やメッセージの検証では、次の作業のいくつかを行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="07cb8-109">In the process of defining schemas and validating messages, you will likely perform some of the following tasks:</span></span>  
  
-   <span data-ttu-id="07cb8-110">構造化された XML メッセージ用スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="07cb8-110">Create schemas for structured XML messages.</span></span>  
  
-   <span data-ttu-id="07cb8-111">フラット ファイル メッセージ用スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="07cb8-111">Create schemas for flat file messages.</span></span>  
  
-   <span data-ttu-id="07cb8-112">整形式 XML のインスタンス データを基にしたスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="07cb8-112">Generate schemas from well-formed XML instance data.</span></span>  
  
-   <span data-ttu-id="07cb8-113">特定のスキーマにメッセージが準拠しているかどうかの検証</span><span class="sxs-lookup"><span data-stu-id="07cb8-113">Validate message conformance to a specific schema.</span></span>  
  
-   <span data-ttu-id="07cb8-114">スキーマのデザイン時検証の実行</span><span class="sxs-lookup"><span data-stu-id="07cb8-114">Perform design-time validation of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07cb8-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="07cb8-115">In This Section</span></span>  
  
-   [<span data-ttu-id="07cb8-116">BizTalk スキーマの種類</span><span class="sxs-lookup"><span data-stu-id="07cb8-116">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)  
  
-   [<span data-ttu-id="07cb8-117">XSD の役割</span><span class="sxs-lookup"><span data-stu-id="07cb8-117">Role of XSD</span></span>](../core/role-of-xsd.md)  
  
-   [<span data-ttu-id="07cb8-118">Web 上の XSD リソース</span><span class="sxs-lookup"><span data-stu-id="07cb8-118">XSD Resources on the Web</span></span>](../core/xsd-resources-on-the-web.md)  
  
-   [<span data-ttu-id="07cb8-119">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="07cb8-119">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)  
  
-   [<span data-ttu-id="07cb8-120">他のスキーマを使用するスキーマ</span><span class="sxs-lookup"><span data-stu-id="07cb8-120">Schemas That Use Other Schemas</span></span>](../core/schemas-that-use-other-schemas.md)  
  
-   [<span data-ttu-id="07cb8-121">型の再利用と派生</span><span class="sxs-lookup"><span data-stu-id="07cb8-121">Type Reuse and Derivations</span></span>](../core/type-reuse-and-derivations.md)  
  
-   [<span data-ttu-id="07cb8-122">BizTalk Server の以前のバージョンからのスキーマの移行</span><span class="sxs-lookup"><span data-stu-id="07cb8-122">Schema Migration from Previous Versions of BizTalk Server</span></span>](../core/schema-migration-from-previous-versions-of-biztalk-server.md)  
  
-   [<span data-ttu-id="07cb8-123">メッセージ処理を制御するメッセージの内容を使用する方法</span><span class="sxs-lookup"><span data-stu-id="07cb8-123">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)  
  
-   [<span data-ttu-id="07cb8-124">Visual Studio でのスキーマの検証</span><span class="sxs-lookup"><span data-stu-id="07cb8-124">Schema Validation in Visual Studio</span></span>](../core/schema-validation-in-visual-studio.md)  
  
-   [<span data-ttu-id="07cb8-125">インスタンス メッセージの生成と検証</span><span class="sxs-lookup"><span data-stu-id="07cb8-125">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)
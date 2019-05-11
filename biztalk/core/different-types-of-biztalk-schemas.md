---
title: BizTalk スキーマの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cabbfc889b4a07616012dc85c6763e1444ed8f43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351081"
---
# <a name="different-types-of-biztalk-schemas"></a><span data-ttu-id="d41dd-102">さまざまな種類の BizTalk スキーマ</span><span class="sxs-lookup"><span data-stu-id="d41dd-102">Different Types of BizTalk Schemas</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d41dd-103">次の 4 種類のスキーマをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d41dd-103">supports the following four types of schemas:</span></span>  
  
- <span data-ttu-id="d41dd-104">**XML スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-104">**XML schema**.</span></span> <span data-ttu-id="d41dd-105">XML スキーマでは、XML インスタンス メッセージのクラスの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-105">An XML schema defines the structure of a class of XML instance messages.</span></span> <span data-ttu-id="d41dd-106">このタイプのスキーマは、XML インスタンス メッセージの構造を定義する XML スキーマ定義 (XSD) 言語を使用して、XSD の使用目的は、このため、このようなスキーマは、簡単な方法で XSD を使用します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-106">Because this type of schema uses XML Schema definition (XSD) language to define the structure of an XML instance message, and this is the intended purpose of XSD, such schemas use XSD in a straightforward way.</span></span>  
  
- <span data-ttu-id="d41dd-107">**フラット ファイル スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-107">**Flat file schema**.</span></span> <span data-ttu-id="d41dd-108">フラット ファイル スキーマは、いくつかの組み合わせまたは区切り文字/位置指定フラット ファイル形式を使用するインスタンス メッセージのクラスの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-108">A flat file schema defines the structure of a class of instance messages that use a flat file format, either delimited or positional or some combination thereof.</span></span> <span data-ttu-id="d41dd-109">XSD のセマンティック固有の機能がすべてのフラット ファイル インスタンス メッセージの構造を定義するための要件に対応できませんので、-など、さまざまな種類の異なるレコード、フラット ファイル内のフィールドの使用可能性のある区切り記号の。BizTalk Server では、XSD の注釈機能を使用して、XSD スキーマ内でこの追加情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-109">Because the native semantic capabilities of XSD do not accommodate all of the requirements for defining the structure of flat file instance messages—such as the various types of delimiters that might be used for different records and fields within the flat file—BizTalk Server uses the annotation capabilities of XSD to store this extra information within an XSD schema.</span></span> <span data-ttu-id="d41dd-110">BizTalk Server では、すべての必要な追加情報を格納するために使用できる注釈タグの豊富なセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-110">BizTalk Server defines a rich set of specific annotation tags that can be used to store all of the required additional information.</span></span>  
  
- <span data-ttu-id="d41dd-111">**エンベロープ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-111">**Envelope schema**.</span></span> <span data-ttu-id="d41dd-112">エンベロープ スキーマは、特殊な種類の XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="d41dd-112">An envelope schema is a special type of XML schema.</span></span> <span data-ttu-id="d41dd-113">エンベロープ スキーマは、1 つまたは複数の XML ビジネス ドキュメントを 1 つの XML インスタンス メッセージにラップするために使用する XML エンベロープの構造の定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d41dd-113">Envelope schemas are used to define the structure of XML envelopes, which are used to wrap one or more XML business documents into a single XML instance message.</span></span> <span data-ttu-id="d41dd-114">エンベロープ スキーマに XML スキーマを定義するときに、いくつかの追加のプロパティの設定が必要なエンベロープ スキーマで定義されている 1 つ以上のルート レコードがあるかどうかなどの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d41dd-114">When you define an XML schema to be an envelope schema, a couple of additional property settings are required, depending on such factors as whether there are more than one root record defined in the envelope schema.</span></span>  
  
- <span data-ttu-id="d41dd-115">**プロパティ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-115">**Property schema**.</span></span> <span data-ttu-id="d41dd-116">プロパティ スキーマは、プロパティの昇格と呼ばれるものの BizTalk Server 内に存在する 2 つのメカニズムのいずれかで使用されます。</span><span class="sxs-lookup"><span data-stu-id="d41dd-116">A property schema is used with one of the two mechanisms that exist within BizTalk Server for what is known as property promotion.</span></span> <span data-ttu-id="d41dd-117">プロパティの昇格は、メッセージ コンテキストに、インスタンス メッセージの内部から特定の値をコピーするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="d41dd-117">Property promotion is the process of copying specific values from deep within an instance message to the message context.</span></span> <span data-ttu-id="d41dd-118">メッセージ コンテキストからこれらの値は、さまざまな BizTalk Server コンポーネントでより簡単にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d41dd-118">From the message context, these values are more easily accessed by various BizTalk Server components.</span></span> <span data-ttu-id="d41dd-119">これらのコンポーネントでは、値を使用して、メッセージのルーティングなどの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-119">These components use the values to perform actions such as message routing.</span></span> <span data-ttu-id="d41dd-120">昇格されたプロパティが、インスタンス メッセージが送信先に送信される直前に、値をインスタンス メッセージの深さに簡単にアクセスできるメッセージ コンテキストから、他の方向にコピーこともできます。</span><span class="sxs-lookup"><span data-stu-id="d41dd-120">Promoted property values can also be copied in the other direction, from the more easily accessible message context back into the depths of the instance message, just before the instance message is sent to its destination.</span></span> <span data-ttu-id="d41dd-121">プロパティ スキーマは、インスタンス メッセージとメッセージ コンテキストの間を行き来昇格させたプロパティをコピーするプロセスで再生する BizTalk スキーマの簡易バージョンです。</span><span class="sxs-lookup"><span data-stu-id="d41dd-121">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span>  
  
  <span data-ttu-id="d41dd-122">セクションの残りの部分は、これらの 4 種類の BizTalk Server でのスキーマに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d41dd-122">The remainder of section provides additional information about these four types of schemas in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d41dd-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d41dd-123">In This Section</span></span>  
  
-   [<span data-ttu-id="d41dd-124">XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="d41dd-124">XML Schemas</span></span>](../core/xml-schemas.md)  
  
-   [<span data-ttu-id="d41dd-125">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d41dd-125">Flat File Schemas</span></span>](../core/flat-file-schemas.md)  
  
-   [<span data-ttu-id="d41dd-126">エンベロープ スキーマ</span><span class="sxs-lookup"><span data-stu-id="d41dd-126">Envelope Schemas</span></span>](../core/envelope-schemas.md)  
  
-   [<span data-ttu-id="d41dd-127">プロパティ スキーマ</span><span class="sxs-lookup"><span data-stu-id="d41dd-127">Property Schemas</span></span>](../core/property-schemas.md)
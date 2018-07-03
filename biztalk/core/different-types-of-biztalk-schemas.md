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
ms.openlocfilehash: 2a60907b3b8bbecf430984ec3a799bc1f91953be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010699"
---
# <a name="different-types-of-biztalk-schemas"></a><span data-ttu-id="2542b-102">さまざまな種類の BizTalk スキーマ</span><span class="sxs-lookup"><span data-stu-id="2542b-102">Different Types of BizTalk Schemas</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2542b-103"> は、次の 4 種類のスキーマをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2542b-103"> supports the following four types of schemas:</span></span>  
  
- <span data-ttu-id="2542b-104">**XML スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="2542b-104">**XML schema**.</span></span> <span data-ttu-id="2542b-105">XML スキーマは XML インスタンス メッセージのクラス構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="2542b-105">An XML schema defines the structure of a class of XML instance messages.</span></span> <span data-ttu-id="2542b-106">このタイプのスキーマでは、XSD (XML Schema Definition) 言語を使って、XML インスタンス メッセージの構造が定義されます。XSD 本来の目的に沿っているため、このスキーマでは、単純な方法で XSD が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2542b-106">Because this type of schema uses XML Schema definition (XSD) language to define the structure of an XML instance message, and this is the intended purpose of XSD, such schemas use XSD in a straightforward way.</span></span>  
  
- <span data-ttu-id="2542b-107">**フラット ファイル スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="2542b-107">**Flat file schema**.</span></span> <span data-ttu-id="2542b-108">フラット ファイル スキーマは、フラット ファイル形式 (区切り文字/位置指定、あるいは、その組み合わせ) を使用したインスタンス メッセージのクラス構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="2542b-108">A flat file schema defines the structure of a class of instance messages that use a flat file format, either delimited or positional or some combination thereof.</span></span> <span data-ttu-id="2542b-109">XSD のセマンティック固有の機能がすべてのフラット ファイル インスタンス メッセージの構造を定義するための要件に対応できませんので、-など、さまざまな種類の異なるレコード、フラット ファイル内のフィールドの使用可能性のある区切り記号の。BizTalk Server では、XSD の注釈機能を使用して、XSD スキーマ内でこの追加情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2542b-109">Because the native semantic capabilities of XSD do not accommodate all of the requirements for defining the structure of flat file instance messages—such as the various types of delimiters that might be used for different records and fields within the flat file—BizTalk Server uses the annotation capabilities of XSD to store this extra information within an XSD schema.</span></span> <span data-ttu-id="2542b-110">BizTalk Server には、必要な補足情報をすべて格納することのできる注釈タグが豊富に定義されています。</span><span class="sxs-lookup"><span data-stu-id="2542b-110">BizTalk Server defines a rich set of specific annotation tags that can be used to store all of the required additional information.</span></span>  
  
- <span data-ttu-id="2542b-111">**エンベロープ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="2542b-111">**Envelope schema**.</span></span> <span data-ttu-id="2542b-112">エンベロープ スキーマは、特殊な XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="2542b-112">An envelope schema is a special type of XML schema.</span></span> <span data-ttu-id="2542b-113">XML ビジネス ドキュメントを単一の XML インスタンス メッセージにラップする XML エンベロープの構造を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2542b-113">Envelope schemas are used to define the structure of XML envelopes, which are used to wrap one or more XML business documents into a single XML instance message.</span></span> <span data-ttu-id="2542b-114">エンベロープ スキーマに XML スキーマを定義するときに、いくつかの追加のプロパティの設定が必要なエンベロープ スキーマで定義されている 1 つ以上のルート レコードがあるかどうかなどの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2542b-114">When you define an XML schema to be an envelope schema, a couple of additional property settings are required, depending on such factors as whether there are more than one root record defined in the envelope schema.</span></span>  
  
- <span data-ttu-id="2542b-115">**プロパティ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="2542b-115">**Property schema**.</span></span> <span data-ttu-id="2542b-116">プロパティ スキーマは、BizTalk Server がプロパティの昇格機能として備えている 2 つのメカニズムのいずれかと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2542b-116">A property schema is used with one of the two mechanisms that exist within BizTalk Server for what is known as property promotion.</span></span> <span data-ttu-id="2542b-117">プロパティの昇格とは、インスタンス メッセージの内部に格納されている特定の値を、メッセージ コンテキストにコピーするプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="2542b-117">Property promotion is the process of copying specific values from deep within an instance message to the message context.</span></span> <span data-ttu-id="2542b-118">各種の BizTalk Server コンポーネントは、メッセージ コンテキストを通じて、これらの値に容易にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2542b-118">From the message context, these values are more easily accessed by various BizTalk Server components.</span></span> <span data-ttu-id="2542b-119">これらのコンポーネントが、メッセージ コンテキスト内の値にアクセスすることで、メッセージのルーティングなどの処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2542b-119">These components use the values to perform actions such as message routing.</span></span> <span data-ttu-id="2542b-120">昇格されたプロパティ値は、インスタンス メッセージを宛先に送る直前に、逆の方向にコピーすることもできます。つまり、プロパティ値をアクセスしやすいメッセージ コンテキストから、インスタンス メッセージの内部に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2542b-120">Promoted property values can also be copied in the other direction, from the more easily accessible message context back into the depths of the instance message, just before the instance message is sent to its destination.</span></span> <span data-ttu-id="2542b-121">プロパティ スキーマは、昇格させたプロパティを、インスタンス メッセージからメッセージ コンテキストへ、あるいは、メッセージ コンテキストからインスタンス メッセージへとコピーするプロセスを実行する、簡易版の BizTalk スキーマといえます。</span><span class="sxs-lookup"><span data-stu-id="2542b-121">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span>  
  
  <span data-ttu-id="2542b-122">以降では、BizTalk Server の 4 種類のスキーマに関する補足情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="2542b-122">The remainder of section provides additional information about these four types of schemas in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2542b-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2542b-123">In This Section</span></span>  
  
-   [<span data-ttu-id="2542b-124">XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="2542b-124">XML Schemas</span></span>](../core/xml-schemas.md)  
  
-   [<span data-ttu-id="2542b-125">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2542b-125">Flat File Schemas</span></span>](../core/flat-file-schemas.md)  
  
-   [<span data-ttu-id="2542b-126">エンベロープ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2542b-126">Envelope Schemas</span></span>](../core/envelope-schemas.md)  
  
-   [<span data-ttu-id="2542b-127">プロパティ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2542b-127">Property Schemas</span></span>](../core/property-schemas.md)
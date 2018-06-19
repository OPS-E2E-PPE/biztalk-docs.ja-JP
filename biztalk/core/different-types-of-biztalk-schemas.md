---
title: BizTalk スキーマの種類 |Microsoft ドキュメント
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
ms.openlocfilehash: 051cd8fb9824cece316ea6f56e318490eacf88c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240282"
---
# <a name="different-types-of-biztalk-schemas"></a><span data-ttu-id="d03a9-102">さまざまな種類の BizTalk スキーマ</span><span class="sxs-lookup"><span data-stu-id="d03a9-102">Different Types of BizTalk Schemas</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d03a9-103"> は、次の 4 種類のスキーマをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d03a9-103"> supports the following four types of schemas:</span></span>  
  
-   <span data-ttu-id="d03a9-104">**XML スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="d03a9-104">**XML schema**.</span></span> <span data-ttu-id="d03a9-105">XML スキーマは XML インスタンス メッセージのクラス構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="d03a9-105">An XML schema defines the structure of a class of XML instance messages.</span></span> <span data-ttu-id="d03a9-106">このタイプのスキーマでは、XSD (XML Schema Definition) 言語を使って、XML インスタンス メッセージの構造が定義されます。XSD 本来の目的に沿っているため、このスキーマでは、単純な方法で XSD が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d03a9-106">Because this type of schema uses XML Schema definition (XSD) language to define the structure of an XML instance message, and this is the intended purpose of XSD, such schemas use XSD in a straightforward way.</span></span>  
  
-   <span data-ttu-id="d03a9-107">**フラット ファイル スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="d03a9-107">**Flat file schema**.</span></span> <span data-ttu-id="d03a9-108">フラット ファイル スキーマは、フラット ファイル形式 (区切り文字/位置指定、あるいは、その組み合わせ) を使用したインスタンス メッセージのクラス構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="d03a9-108">A flat file schema defines the structure of a class of instance messages that use a flat file format, either delimited or positional or some combination thereof.</span></span> <span data-ttu-id="d03a9-109">XSD のネイティブのセマンティック機能に対応していませんフラット ファイル インスタンス メッセージの構造を定義するための要件をすべてため — さまざまな種類の異なるレコードと、フラット ファイル内のフィールドを使用する区切り記号のなど。BizTalk Server では、XSD の注釈機能を使用して、XSD スキーマ内でこの追加情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d03a9-109">Because the native semantic capabilities of XSD do not accommodate all of the requirements for defining the structure of flat file instance messages—such as the various types of delimiters that might be used for different records and fields within the flat file—BizTalk Server uses the annotation capabilities of XSD to store this extra information within an XSD schema.</span></span> <span data-ttu-id="d03a9-110">BizTalk Server には、必要な補足情報をすべて格納することのできる注釈タグが豊富に定義されています。</span><span class="sxs-lookup"><span data-stu-id="d03a9-110">BizTalk Server defines a rich set of specific annotation tags that can be used to store all of the required additional information.</span></span>  
  
-   <span data-ttu-id="d03a9-111">**エンベロープ スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="d03a9-111">**Envelope schema**.</span></span> <span data-ttu-id="d03a9-112">エンベロープ スキーマは、特殊な XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="d03a9-112">An envelope schema is a special type of XML schema.</span></span> <span data-ttu-id="d03a9-113">XML ビジネス ドキュメントを単一の XML インスタンス メッセージにラップする XML エンベロープの構造を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d03a9-113">Envelope schemas are used to define the structure of XML envelopes, which are used to wrap one or more XML business documents into a single XML instance message.</span></span> <span data-ttu-id="d03a9-114">追加のプロパティ設定がいくつかが必要にエンベロープ スキーマに XML スキーマを定義するときは、エンベロープ スキーマで定義されている 1 つ以上のルート レコードがあるかどうかなどの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d03a9-114">When you define an XML schema to be an envelope schema, a couple of additional property settings are required, depending on such factors as whether there are more than one root record defined in the envelope schema.</span></span>  
  
-   <span data-ttu-id="d03a9-115">**プロパティ スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="d03a9-115">**Property schema**.</span></span> <span data-ttu-id="d03a9-116">プロパティ スキーマは、BizTalk Server がプロパティの昇格機能として備えている 2 つのメカニズムのいずれかと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="d03a9-116">A property schema is used with one of the two mechanisms that exist within BizTalk Server for what is known as property promotion.</span></span> <span data-ttu-id="d03a9-117">プロパティの昇格とは、インスタンス メッセージの内部に格納されている特定の値を、メッセージ コンテキストにコピーするプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="d03a9-117">Property promotion is the process of copying specific values from deep within an instance message to the message context.</span></span> <span data-ttu-id="d03a9-118">各種の BizTalk Server コンポーネントは、メッセージ コンテキストを通じて、これらの値に容易にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d03a9-118">From the message context, these values are more easily accessed by various BizTalk Server components.</span></span> <span data-ttu-id="d03a9-119">これらのコンポーネントが、メッセージ コンテキスト内の値にアクセスすることで、メッセージのルーティングなどの処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d03a9-119">These components use the values to perform actions such as message routing.</span></span> <span data-ttu-id="d03a9-120">昇格されたプロパティ値は、インスタンス メッセージを宛先に送る直前に、逆の方向にコピーすることもできます。つまり、プロパティ値をアクセスしやすいメッセージ コンテキストから、インスタンス メッセージの内部に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d03a9-120">Promoted property values can also be copied in the other direction, from the more easily accessible message context back into the depths of the instance message, just before the instance message is sent to its destination.</span></span> <span data-ttu-id="d03a9-121">プロパティ スキーマは、昇格させたプロパティを、インスタンス メッセージからメッセージ コンテキストへ、あるいは、メッセージ コンテキストからインスタンス メッセージへとコピーするプロセスを実行する、簡易版の BizTalk スキーマといえます。</span><span class="sxs-lookup"><span data-stu-id="d03a9-121">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span>  
  
 <span data-ttu-id="d03a9-122">以降では、BizTalk Server の 4 種類のスキーマに関する補足情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="d03a9-122">The remainder of section provides additional information about these four types of schemas in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d03a9-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d03a9-123">In This Section</span></span>  
  
-   [<span data-ttu-id="d03a9-124">XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="d03a9-124">XML Schemas</span></span>](../core/xml-schemas.md)  
  
-   [<span data-ttu-id="d03a9-125">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d03a9-125">Flat File Schemas</span></span>](../core/flat-file-schemas.md)  
  
-   [<span data-ttu-id="d03a9-126">エンベロープ スキーマ</span><span class="sxs-lookup"><span data-stu-id="d03a9-126">Envelope Schemas</span></span>](../core/envelope-schemas.md)  
  
-   [<span data-ttu-id="d03a9-127">プロパティ スキーマ</span><span class="sxs-lookup"><span data-stu-id="d03a9-127">Property Schemas</span></span>](../core/property-schemas.md)
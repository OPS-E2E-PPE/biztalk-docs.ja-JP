---
title: SWIFT テキスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, text
ms.assetid: 90851d38-7789-4b1b-813b-7943f77ab984
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c80d8ee0343cbf8ac96d57119ef198d623159b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214522"
---
# <a name="swift-text"></a><span data-ttu-id="66981-102">SWIFT テキスト</span><span class="sxs-lookup"><span data-stu-id="66981-102">SWIFT Text</span></span>
<span data-ttu-id="66981-103">メッセージ テキスト、財務 (FIN) メッセージのペイロードとすべての送信者、受信者、およびメッセージの種類を含むフィールドを除くデータ フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66981-103">The message text makes up the payload of the financial (FIN) message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="66981-104">これら 3 つのフィールドは、ヘッダー部分に含まれます。</span><span class="sxs-lookup"><span data-stu-id="66981-104">These three fields are contained in the header portion.</span></span> <span data-ttu-id="66981-105">一部のメッセージには、処理情報も提供する、オプションのユーザー ヘッダーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="66981-105">Some messages also contain an optional User Header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="66981-106">各 FIN メッセージ ペイロードは、一連のフィールドに定義されたシーケンス内で構成されます。</span><span class="sxs-lookup"><span data-stu-id="66981-106">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="66981-107">これらのフィールドは、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="66981-107">These fields conform to the following rules:</span></span>  
  
-   <span data-ttu-id="66981-108">フィールドには、必須または、シーケンス内でオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="66981-108">The fields may be required or optional within the sequence.</span></span>  
  
-   <span data-ttu-id="66981-109">シーケンスは、のサブシーケンスを含めることができ、サブシーケンスがシーケンス内で繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="66981-109">A sequence may contain subsequences, and a subsequence may repeat within a sequence.</span></span>  
  
-   <span data-ttu-id="66981-110">いくつかのメッセージ型のフィールドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="66981-110">You can use a field in several message types.</span></span>  
  
-   <span data-ttu-id="66981-111">フィールドの内部に、要素またはサブフィールドが可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66981-111">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="66981-112">要素またはサブフィールドをいくつかのフィールドに一般的な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66981-112">An element or subfield may be common to several fields.</span></span>  
  
-   <span data-ttu-id="66981-113">各繰り返しシーケンスは、グループ ノードで表されます。</span><span class="sxs-lookup"><span data-stu-id="66981-113">Each repeating sequence is represented by a group node.</span></span>  
  
-   <span data-ttu-id="66981-114">各フィールド自体があります、複数の節レベル レコードとして各説明します。</span><span class="sxs-lookup"><span data-stu-id="66981-114">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
-   <span data-ttu-id="66981-115">スキーマ要素は、最下位レベルのサブフィールドのみを表します。</span><span class="sxs-lookup"><span data-stu-id="66981-115">A schema element represents only the lowest level subfield.</span></span>  
  
-   <span data-ttu-id="66981-116">共通のレコードと要素は、以下に示すよう共通および基本のスキーマで定義されます。</span><span class="sxs-lookup"><span data-stu-id="66981-116">Common records and elements are defined in the common and base schema, as described below.</span></span>  
  
-   <span data-ttu-id="66981-117">一部のフィールドは、(パーティ フィールドなど) のいくつかの形式で表すことができます。</span><span class="sxs-lookup"><span data-stu-id="66981-117">Some fields may be represented in several formats (such as party fields).</span></span> <span data-ttu-id="66981-118">このようなフィールドは、スキーマの選択フィールドとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="66981-118">Such fields are defined as choice fields in the schema.</span></span>  
  
 <span data-ttu-id="66981-119">一部のフィールドには、値のセットが制限されます。</span><span class="sxs-lookup"><span data-stu-id="66981-119">Some fields have limited sets of values.</span></span> <span data-ttu-id="66981-120">ほとんどの場合、スキーマには、これらの値が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="66981-120">For the most part, the schema lists these values.</span></span> <span data-ttu-id="66981-121">スキーマ定義には、文字セットの検証も含まれます。</span><span class="sxs-lookup"><span data-stu-id="66981-121">Schema definitions also include character set validation.</span></span>
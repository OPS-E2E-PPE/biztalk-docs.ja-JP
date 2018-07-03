---
title: SWIFT テキスト |Microsoft Docs
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
ms.openlocfilehash: 06e46c8be5da2f62f2b59ce2591e0559367adf08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990931"
---
# <a name="swift-text"></a><span data-ttu-id="870e0-102">SWIFT テキスト</span><span class="sxs-lookup"><span data-stu-id="870e0-102">SWIFT Text</span></span>
<span data-ttu-id="870e0-103">メッセージ テキストは、財務 (FIN)、メッセージのペイロードおり、すべての送信者、受信者、およびメッセージの種類を含むフィールドを除くデータ フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="870e0-103">The message text makes up the payload of the financial (FIN) message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="870e0-104">ヘッダー部分は、これら 3 つのフィールドに格納されます。</span><span class="sxs-lookup"><span data-stu-id="870e0-104">These three fields are contained in the header portion.</span></span> <span data-ttu-id="870e0-105">一部のメッセージには、処理情報を入力することの省略可能なユーザー ヘッダーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="870e0-105">Some messages also contain an optional User Header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="870e0-106">各 FIN メッセージのペイロードは、一連の定義された一連のフィールドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="870e0-106">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="870e0-107">これらのフィールドは、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="870e0-107">These fields conform to the following rules:</span></span>  
  
- <span data-ttu-id="870e0-108">必須またはオプション、シーケンス内のフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="870e0-108">The fields may be required or optional within the sequence.</span></span>  
  
- <span data-ttu-id="870e0-109">シーケンスは、のサブシーケンスを含めることができ、サブシーケンスがシーケンス内で繰り返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="870e0-109">A sequence may contain subsequences, and a subsequence may repeat within a sequence.</span></span>  
  
- <span data-ttu-id="870e0-110">いくつかのメッセージの種類のフィールドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="870e0-110">You can use a field in several message types.</span></span>  
  
- <span data-ttu-id="870e0-111">フィールドの内部、要素またはサブフィールドに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="870e0-111">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="870e0-112">要素またはサブフィールドをいくつかのフィールドに共通可能性があります。</span><span class="sxs-lookup"><span data-stu-id="870e0-112">An element or subfield may be common to several fields.</span></span>  
  
- <span data-ttu-id="870e0-113">各繰り返しシーケンスは、グループ ノードで表されます。</span><span class="sxs-lookup"><span data-stu-id="870e0-113">Each repeating sequence is represented by a group node.</span></span>  
  
- <span data-ttu-id="870e0-114">各フィールド自体があります、複数の節レベル レコードとして各説明。</span><span class="sxs-lookup"><span data-stu-id="870e0-114">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
- <span data-ttu-id="870e0-115">スキーマ要素は、最下位レベルのサブフィールドのみを表します。</span><span class="sxs-lookup"><span data-stu-id="870e0-115">A schema element represents only the lowest level subfield.</span></span>  
  
- <span data-ttu-id="870e0-116">共通のレコードと要素は、以下に示すよう、共通の基本とスキーマで定義されます。</span><span class="sxs-lookup"><span data-stu-id="870e0-116">Common records and elements are defined in the common and base schema, as described below.</span></span>  
  
- <span data-ttu-id="870e0-117">(パーティのフィールド) などのいくつかの形式では、いくつかのフィールドを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="870e0-117">Some fields may be represented in several formats (such as party fields).</span></span> <span data-ttu-id="870e0-118">このようなフィールドは、スキーマの選択フィールドとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="870e0-118">Such fields are defined as choice fields in the schema.</span></span>  
  
  <span data-ttu-id="870e0-119">一部のフィールドには、値のセットが制限されます。</span><span class="sxs-lookup"><span data-stu-id="870e0-119">Some fields have limited sets of values.</span></span> <span data-ttu-id="870e0-120">ほとんどの場合、スキーマには、これらの値が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="870e0-120">For the most part, the schema lists these values.</span></span> <span data-ttu-id="870e0-121">スキーマの定義には、文字セットの検証も含まれます。</span><span class="sxs-lookup"><span data-stu-id="870e0-121">Schema definitions also include character set validation.</span></span>
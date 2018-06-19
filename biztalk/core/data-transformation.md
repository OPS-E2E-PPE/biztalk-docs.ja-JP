---
title: データ変換 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, data translation
- data translation, about data translation
- data transformation, about data transformation
- maps, data transformation
- data transformation, maps
- data translation, maps
ms.assetid: a6aa5e9a-8d9c-478d-8f69-f9b16ed1a18c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ee1cd9b7e825f210032f7caaaa292496cfa44c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238650"
---
# <a name="data-transformation"></a><span data-ttu-id="d2e18-102">[データの変換]</span><span class="sxs-lookup"><span data-stu-id="d2e18-102">Data Transformation</span></span>
<span data-ttu-id="d2e18-103">データのマッピングは、データのトランスフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d2e18-103">Mapping data relies on data transformation.</span></span>  
  
 <span data-ttu-id="d2e18-104">トランスフォームは、送信元スキーマと送信先スキーマ間のさまざまなレコードやフィールドについて、両者の対応関係を作成するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="d2e18-104">Data transformation is the process of creating a correspondence between records and fields of a source schema to (often different) records and fields in a destination schema.</span></span> <span data-ttu-id="d2e18-105">たとえば、注文書に含まれる出荷先や請求先の住所情報を請求書にマッピングする場合にトランスフォームが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2e18-105">An example of data transformation is to map shipping and billing address information from a purchase order to an invoice.</span></span> <span data-ttu-id="d2e18-106">これは、最も基本的なタイプのマッピングです。</span><span class="sxs-lookup"><span data-stu-id="d2e18-106">This is the most basic type of mapping.</span></span> <span data-ttu-id="d2e18-107">トランスフォームは、次のような操作に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2e18-107">Data transformation can also apply to operations such as:</span></span>  
  
-   <span data-ttu-id="d2e18-108">ループ レコードから平均データを割り出し、その出力を送信先スキーマの単一フィールドに送る。</span><span class="sxs-lookup"><span data-stu-id="d2e18-108">Averaging data from a looping record and sending the output to a single field in the destination schema.</span></span>  
  
-   <span data-ttu-id="d2e18-109">文字データを ASCII 形式に変換する。</span><span class="sxs-lookup"><span data-stu-id="d2e18-109">Converting character data to its ASCII format.</span></span>  
  
-   <span data-ttu-id="d2e18-110">1 つまたは複数のレコードに対して加算または減算を適用し、その結果を送信先スキーマの単一フィールドに出力する。</span><span class="sxs-lookup"><span data-stu-id="d2e18-110">Adding or subtracting data from one or more records and putting the result in a single field in the destination schema.</span></span>  
  
 <span data-ttu-id="d2e18-111">データを 1 つの形式から別の形式に変換する場合は、パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2e18-111">If you want to translate data from one format to another, you would use a pipeline.</span></span> <span data-ttu-id="d2e18-112">パイプラインは、エンタープライズ アプリケーション統合の問題を解決するために、特定の種類のメッセージを、既存のシステムで利用可能な別の形式に変換する必要があり、マップではそれを行うことができない場合に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="d2e18-112">This can be helpful in solving enterprise application integration problems by translating a given type of message into alternative formats required by existing systems but cannot be done using a map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e18-113">参照</span><span class="sxs-lookup"><span data-stu-id="d2e18-113">See Also</span></span>  
 <span data-ttu-id="d2e18-114">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="d2e18-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="d2e18-115">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2e18-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)
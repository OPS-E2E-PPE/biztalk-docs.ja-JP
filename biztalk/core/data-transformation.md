---
title: データ変換 |Microsoft Docs
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
ms.openlocfilehash: 570f3582fa13c116039f7ff965b72b14de84cc56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389780"
---
# <a name="data-transformation"></a><span data-ttu-id="990e6-102">[データの変換]</span><span class="sxs-lookup"><span data-stu-id="990e6-102">Data Transformation</span></span>
<span data-ttu-id="990e6-103">データのマッピングは、データのトランスフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="990e6-103">Mapping data relies on data transformation.</span></span>  
  
 <span data-ttu-id="990e6-104">トランスフォームは、送信元スキーマと送信先スキーマ間のさまざまなレコードやフィールドについて、両者の対応関係を作成するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="990e6-104">Data transformation is the process of creating a correspondence between records and fields of a source schema to (often different) records and fields in a destination schema.</span></span> <span data-ttu-id="990e6-105">たとえば、注文書に含まれる出荷先や請求先の住所情報を請求書にマッピングする場合にトランスフォームが使用されます。</span><span class="sxs-lookup"><span data-stu-id="990e6-105">An example of data transformation is to map shipping and billing address information from a purchase order to an invoice.</span></span> <span data-ttu-id="990e6-106">これは、最も基本的なタイプのマッピングです。</span><span class="sxs-lookup"><span data-stu-id="990e6-106">This is the most basic type of mapping.</span></span> <span data-ttu-id="990e6-107">トランスフォームは、次のような操作に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="990e6-107">Data transformation can also apply to operations such as:</span></span>  
  
- <span data-ttu-id="990e6-108">ループ レコードから平均データを割り出し、その出力を送信先スキーマの単一フィールドに送る。</span><span class="sxs-lookup"><span data-stu-id="990e6-108">Averaging data from a looping record and sending the output to a single field in the destination schema.</span></span>  
  
- <span data-ttu-id="990e6-109">文字データを ASCII 形式に変換する。</span><span class="sxs-lookup"><span data-stu-id="990e6-109">Converting character data to its ASCII format.</span></span>  
  
- <span data-ttu-id="990e6-110">1 つまたは複数のレコードに対して加算または減算を適用し、その結果を送信先スキーマの単一フィールドに出力する。</span><span class="sxs-lookup"><span data-stu-id="990e6-110">Adding or subtracting data from one or more records and putting the result in a single field in the destination schema.</span></span>  
  
  <span data-ttu-id="990e6-111">データを 1 つの形式から別の形式に変換する場合は、パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="990e6-111">If you want to translate data from one format to another, you would use a pipeline.</span></span> <span data-ttu-id="990e6-112">パイプラインは、エンタープライズ アプリケーション統合の問題を解決するために、特定の種類のメッセージを、既存のシステムで利用可能な別の形式に変換する必要があり、マップではそれを行うことができない場合に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="990e6-112">This can be helpful in solving enterprise application integration problems by translating a given type of message into alternative formats required by existing systems but cannot be done using a map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="990e6-113">参照</span><span class="sxs-lookup"><span data-stu-id="990e6-113">See Also</span></span>  
 <span data-ttu-id="990e6-114">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="990e6-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="990e6-115">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="990e6-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)
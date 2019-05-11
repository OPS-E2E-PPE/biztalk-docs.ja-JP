---
title: エラー - の 2 番目の入力テーブル抽出 Functoid へ有効 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c53e84e62422a70214a4cfd90979de85538e158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388435"
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a><span data-ttu-id="ecdb0-102">エラー - の 2 番目の入力テーブル抽出 Functoid へ無効です</span><span class="sxs-lookup"><span data-stu-id="ecdb0-102">Error - Second Input for Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="ecdb0-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ecdb0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ecdb0-104">btm1073</span><span class="sxs-lookup"><span data-stu-id="ecdb0-104">btm1073</span></span>  
  
 <span data-ttu-id="ecdb0-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="ecdb0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ecdb0-106">2 番目の入力パラメーターを関連する**テーブル抽出**functoid が無効です。</span><span class="sxs-lookup"><span data-stu-id="ecdb0-106">The second input parameter to the relevant **Table Extractor** functoid is not valid.</span></span> <span data-ttu-id="ecdb0-107">このパラメーターは、テーブル ループ グリッド用に構成された有効な列を示す正の整数定数である必要があります、**テーブル ループ**functoid の最初の入力パラメーターで示されます。</span><span class="sxs-lookup"><span data-stu-id="ecdb0-107">This parameter must be a positive integer constant that indicates a valid column in the table looping grid configured for the **Table Looping** functoid that is indicated by the first input parameter.</span></span>  
  
 <span data-ttu-id="ecdb0-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="ecdb0-108">**User Action**</span></span>  
  
 <span data-ttu-id="ecdb0-109">入力パラメーターを関連することを確認**テーブル抽出**functoid を使用してアクセスその**入力パラメーター**プロパティおよび**構成\<Functoid\>Functoid**ダイアログ ボックスでは、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="ecdb0-109">Ensure that the input parameters to the relevant **Table Extractor** functoid, as accessed through its **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="ecdb0-110">テーブル抽出 functoid の入力パラメーター番号</span><span class="sxs-lookup"><span data-stu-id="ecdb0-110">Table Extractor functoid input parameter number</span></span>|<span data-ttu-id="ecdb0-111">説明</span><span class="sxs-lookup"><span data-stu-id="ecdb0-111">Description</span></span>|  
|-----------------------------------------------------|-----------------|  
|<span data-ttu-id="ecdb0-112">1</span><span class="sxs-lookup"><span data-stu-id="ecdb0-112">1</span></span>|<span data-ttu-id="ecdb0-113">リンク、**テーブル ループ**元である functoid**テーブル抽出**functoid が 2 番目のパラメーターで示されている列のデータをプルします。</span><span class="sxs-lookup"><span data-stu-id="ecdb0-113">Link from the **Table Looping** functoid from which this **Table Extractor** functoid will pull column data as indicated by its second parameter.</span></span>|  
|<span data-ttu-id="ecdb0-114">2</span><span class="sxs-lookup"><span data-stu-id="ecdb0-114">2</span></span>|<span data-ttu-id="ecdb0-115">使用して構成データのテーブルで有効な列の数、**テーブル ループ グリッド**のプロパティ、**テーブル ループ**functoid の最初の入力パラメーターで指定します。</span><span class="sxs-lookup"><span data-stu-id="ecdb0-115">The number of a valid column in the data table configured through the **Table Looping Grid** property of the **Table Looping** functoid specified by the first input parameter.</span></span>|
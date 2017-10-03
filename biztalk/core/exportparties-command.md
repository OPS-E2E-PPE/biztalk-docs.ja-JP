---
title: "ExportParties コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b421c8ed-d505-48ba-9d1d-8519c9d51750
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca525872ccc1cd941673189c4ac176fc4631f22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exportparties-command"></a><span data-ttu-id="daf7f-102">ExportParties コマンド</span><span class="sxs-lookup"><span data-stu-id="daf7f-102">ExportParties Command</span></span>
<span data-ttu-id="daf7f-103">すべてのパーティとアグリーメントを XML バインド ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="daf7f-103">Exports all the parties and agreements to an XML bindings file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="daf7f-104">このコマンドは、以降で新しい **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、および以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="daf7f-104">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>

## <a name="usage"></a><span data-ttu-id="daf7f-105">使用方法</span><span class="sxs-lookup"><span data-stu-id="daf7f-105">Usage</span></span>
  <span data-ttu-id="daf7f-106">**BTSTask ExportParties-宛先**:*値*[**-サーバー**:*値*] [**-データベース**:*値*]</span><span class="sxs-lookup"><span data-stu-id="daf7f-106">**BTSTask ExportParties -Destination**:*value* [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="daf7f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="daf7f-107">Parameters</span></span>

|<span data-ttu-id="daf7f-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="daf7f-108">Parameter</span></span>|<span data-ttu-id="daf7f-109">必須</span><span class="sxs-lookup"><span data-stu-id="daf7f-109">Required</span></span>|<span data-ttu-id="daf7f-110">値</span><span class="sxs-lookup"><span data-stu-id="daf7f-110">Value</span></span>|  
|---|---|---|  
| <span data-ttu-id="daf7f-111">**変換先**</span><span class="sxs-lookup"><span data-stu-id="daf7f-111">**-Destination**</span></span> | <span data-ttu-id="daf7f-112">必須</span><span class="sxs-lookup"><span data-stu-id="daf7f-112">Required</span></span> | <span data-ttu-id="daf7f-113">書き込み先 XML バインド ファイルのパスとファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="daf7f-113">Path and file name of the XML binding file to write.</span></span> |
| <span data-ttu-id="daf7f-114">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="daf7f-114">**-Server**</span></span> | <span data-ttu-id="daf7f-115">省略可</span><span class="sxs-lookup"><span data-stu-id="daf7f-115">Optional</span></span> | <span data-ttu-id="daf7f-116">BizTalk 構成データベースをホストする SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="daf7f-116">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="daf7f-117">**複数のデータベース**</span><span class="sxs-lookup"><span data-stu-id="daf7f-117">**-Database**</span></span> | <span data-ttu-id="daf7f-118">省略可</span><span class="sxs-lookup"><span data-stu-id="daf7f-118">Optional</span></span> | <span data-ttu-id="daf7f-119">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="daf7f-119">The name of the BizTalk configuration database.</span></span>|

## <a name="sample"></a><span data-ttu-id="daf7f-120">サンプル</span><span class="sxs-lookup"><span data-stu-id="daf7f-120">Sample</span></span>
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a><span data-ttu-id="daf7f-121">解説</span><span class="sxs-lookup"><span data-stu-id="daf7f-121">Remarks</span></span>
  <span data-ttu-id="daf7f-122">パーティ、アグリーメント、および EDI フォールバックの設定のみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="daf7f-122">Only parties, agreements, and EDI fallback settings are exported.</span></span> <span data-ttu-id="daf7f-123">アプリケーションのアイテムはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="daf7f-123">No application artifacts are exported.</span></span>

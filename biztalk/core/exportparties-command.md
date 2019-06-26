---
title: ExportParties コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b421c8ed-d505-48ba-9d1d-8519c9d51750
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63245cf72306af5bb4c28552a037ce89d8e6bfe8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345912"
---
# <a name="exportparties-command"></a><span data-ttu-id="61013-102">ExportParties コマンド</span><span class="sxs-lookup"><span data-stu-id="61013-102">ExportParties Command</span></span>
<span data-ttu-id="61013-103">すべてのパーティーと契約を XML バインド ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="61013-103">Exports all the parties and agreements to an XML bindings file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61013-104">このコマンドは、以降では新しい **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、およびそれ以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="61013-104">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>

## <a name="usage"></a><span data-ttu-id="61013-105">使用方法</span><span class="sxs-lookup"><span data-stu-id="61013-105">Usage</span></span>
  <span data-ttu-id="61013-106">**BTSTask ExportParties -Destination**:*value* [ **-Server**:*value*] [ **-Database**:*value*]</span><span class="sxs-lookup"><span data-stu-id="61013-106">**BTSTask ExportParties -Destination**:*value* [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="61013-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61013-107">Parameters</span></span>

|<span data-ttu-id="61013-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61013-108">Parameter</span></span>|<span data-ttu-id="61013-109">必須</span><span class="sxs-lookup"><span data-stu-id="61013-109">Required</span></span>|<span data-ttu-id="61013-110">値</span><span class="sxs-lookup"><span data-stu-id="61013-110">Value</span></span>|  
|---|---|---|  
| <span data-ttu-id="61013-111">**変換先**</span><span class="sxs-lookup"><span data-stu-id="61013-111">**-Destination**</span></span> | <span data-ttu-id="61013-112">必須</span><span class="sxs-lookup"><span data-stu-id="61013-112">Required</span></span> | <span data-ttu-id="61013-113">書き込む XML バインド ファイルのパスとファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="61013-113">Path and file name of the XML binding file to write.</span></span> |
| <span data-ttu-id="61013-114">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="61013-114">**-Server**</span></span> | <span data-ttu-id="61013-115">省略可</span><span class="sxs-lookup"><span data-stu-id="61013-115">Optional</span></span> | <span data-ttu-id="61013-116">BizTalk 構成データベースをホストする SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="61013-116">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="61013-117">**-データベース**</span><span class="sxs-lookup"><span data-stu-id="61013-117">**-Database**</span></span> | <span data-ttu-id="61013-118">省略可</span><span class="sxs-lookup"><span data-stu-id="61013-118">Optional</span></span> | <span data-ttu-id="61013-119">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="61013-119">The name of the BizTalk configuration database.</span></span>|

## <a name="sample"></a><span data-ttu-id="61013-120">サンプル</span><span class="sxs-lookup"><span data-stu-id="61013-120">Sample</span></span>
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a><span data-ttu-id="61013-121">コメント</span><span class="sxs-lookup"><span data-stu-id="61013-121">Remarks</span></span>
  <span data-ttu-id="61013-122">パーティ、契約、および EDI フォールバックの設定のみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="61013-122">Only parties, agreements, and EDI fallback settings are exported.</span></span> <span data-ttu-id="61013-123">アプリケーション アイテムはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="61013-123">No application artifacts are exported.</span></span>

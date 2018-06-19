---
title: ExportParties コマンド |Microsoft ドキュメント
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
ms.openlocfilehash: 6ca525872ccc1cd941673189c4ac176fc4631f22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245818"
---
# <a name="exportparties-command"></a>ExportParties コマンド
すべてのパーティとアグリーメントを XML バインド ファイルにエクスポートします。

> [!IMPORTANT]
> このコマンドは、以降で新しい **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、および以降のバージョン。

## <a name="usage"></a>使用方法
  **BTSTask ExportParties-宛先**:*値*[**-サーバー**:*値*] [**-データベース**:*値*]
  
## <a name="parameters"></a>パラメーター

|パラメーター|必須|値|  
|---|---|---|  
| **変換先** | 必須 | 書き込み先 XML バインド ファイルのパスとファイルの名前。 |
| **-サーバー** | 省略可 | BizTalk 構成データベースをホストする SQL server の名前。 |
| **複数のデータベース** | 省略可 | BizTalk 構成データベースの名前。|

## <a name="sample"></a>サンプル
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a>解説
  パーティ、アグリーメント、および EDI フォールバックの設定のみがエクスポートされます。 アプリケーションのアイテムはエクスポートされません。

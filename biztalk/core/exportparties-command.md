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
# <a name="exportparties-command"></a>ExportParties コマンド
すべてのパーティーと契約を XML バインド ファイルにエクスポートします。

> [!IMPORTANT]
> このコマンドは、以降では新しい **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、およびそれ以降のバージョン。

## <a name="usage"></a>使用方法
  **BTSTask ExportParties -Destination**:*value* [ **-Server**:*value*] [ **-Database**:*value*]
  
## <a name="parameters"></a>パラメーター

|パラメーター|必須|値|  
|---|---|---|  
| **変換先** | 必須 | 書き込む XML バインド ファイルのパスとファイルの名前。 |
| **-サーバー** | 省略可 | BizTalk 構成データベースをホストする SQL server の名前。 |
| **-データベース** | 省略可 | BizTalk 構成データベースの名前。|

## <a name="sample"></a>サンプル
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a>コメント
  パーティ、契約、および EDI フォールバックの設定のみがエクスポートされます。 アプリケーション アイテムはエクスポートされません。

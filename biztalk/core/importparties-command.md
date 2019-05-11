---
title: ImportParties コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09e59f51aa6d99fbd9b1351087a403350cc22a1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382210"
---
# <a name="importparties-command"></a>ImportParties コマンド
アプリケーションのアイテムのいずれかをインポートせず、構成データベース内のソース XML バインド ファイルからの企業間取引のパーティーと契約をインポートします。 詳細については、次を参照してください。**解説**このトピックの「します。  

> [!IMPORTANT]
> このコマンドは、以降では新しい**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**、およびそれ以降のバージョン。
> 
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で生成されたバインド ファイルでは、アプリケーションが指定されません。 これらは、既定のアプリケーションにインポートされます。  
  
## <a name="usage"></a>使用方法  
  **BTSTask ImportParties -Source**:*value* **[-ExcludeEdiFallbackSettings]** [**-Server**:*value*] [**-Database**:*value*]
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---|---|---|  
|**-ソース** | 必須 | 読み取る XML バインド ファイルのパスとファイル名。|
|**-ExcludeEdiFallbackSettings** | 省略可 | 指定した場合は、バインド ファイルから edi フォールバック (x12 および edifact) の設定を除外します。  |
| **-サーバー** | 省略可 | BizTalk 構成データベースをホストする SQL server の名前。 |
| **-データベース** | 省略可 | BizTalk 構成データベースの名前。 |

## <a name="sample"></a>サンプル
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a>コメント
アプリケーション アイテムも、バインド ファイルにある場合、それらはインポートされません。 パーティーと契約だけがインポートされます。
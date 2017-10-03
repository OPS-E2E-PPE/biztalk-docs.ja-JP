---
title: "ImportParties コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15edad97134d3dbccc6f4b1af9395cb0bc01febd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importparties-command"></a>ImportParties コマンド
企業間取引パーティとアグリーメントをアプリケーションのアイテムのいずれかをインポートすることがなく、構成データベース内のソース XML バインド ファイルからインポートします。 詳細については、次を参照してください。**解説**」を参照します。  

> [!IMPORTANT]
> このコマンドは、以降で新しい **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、および以降のバージョン。
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で生成されたバインド ファイルでは、アプリケーションが指定されません。 これらは、既定のアプリケーションにインポートされます。  
  
## <a name="usage"></a>使用方法  
  **BTSTask ImportParties-ソース**:*値*[**- ExcludeEdiFallbackSettings**] [**-サーバー**:*値*] [**-データベース**:*値*]
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---|---|---|  
|**ソース** | 必須 | 読み取る XML バインド ファイルのパスとファイル名。|
|**-ExcludeEdiFallbackSettings** | 省略可 | 指定した場合は、バインド ファイルから edi フォールバック (x12 および edifact) の設定を除外します。  |
| **-サーバー** | 省略可 | BizTalk 構成データベースをホストする SQL server の名前。 |
| **複数のデータベース** | 省略可 | BizTalk 構成データベースの名前。 |

## <a name="sample"></a>サンプル
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a>解説
バインド ファイルには、アプリケーションのアイテムもがある場合、それらはインポートされません。 パーティとアグリーメントだけがインポートされます。
---
title: 追跡プロファイルの展開ユーティリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 672879df2c1c5217d8a9710dad000609dd95d0c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974112"
---
# <a name="tracking-profile-deployment-utility"></a>追跡プロファイルの展開ユーティリティ
開発者は、bttdeploy ユーティリティを使用して、追跡プロファイルを BAM インフラストラクチャに適用したり、追跡プロファイルを BAM インフラストラクチャから削除したりできます。 追跡プロファイル エディター (TPE) で、[追跡プロファイルの適用] メニュー オプションをクリックしても、bttdeploy ユーティリティと同じ機能を使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
 **使用方法**  
  
 **bttdeploy.exe [オプション] のファイル名**  
  
|オプション|Description|  
|------------|-----------------|  
|/h または /?|省略可能: bttdeploy の構文を表示します。|  
|/mgdb\<サーバー名 [, ポート]\>\\< データベース名\>|省略可能: 管理サーバー、ポート、およびプロファイルを適用するデータベース名を指定します。 **注:** このパラメーターを使用する場合、ポートは省略可能です。|  
|/remove|省略可能: は、追跡プロファイルは、BAM データベースから削除することを指定します。|  
|filename|適用または削除する追跡プロファイルのファイル名です。|  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)   
 [孤立した追跡プロファイルを削除する方法](../core/how-to-remove-orphaned-tracking-profiles.md)
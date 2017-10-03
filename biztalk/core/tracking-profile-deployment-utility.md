---
title: "追跡プロファイルの展開ユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c4d261069b83741413e255a3f8bacd6dd9260d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
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
|/mgdb\<サーバー名 [, ポート] >\\< データベース名\>|省略可能: 管理サーバー、ポート、およびプロファイルを適用するデータベース名を指定します。 **注:**このパラメーターを使用する場合、ポートは省略可能です。|  
|/remove|省略可能: は、追跡プロファイルは、BAM データベースから削除することを指定します。|  
|filename|適用または削除する追跡プロファイルのファイル名です。|  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)   
 [孤立した追跡プロファイルを削除する方法](../core/how-to-remove-orphaned-tracking-profiles.md)
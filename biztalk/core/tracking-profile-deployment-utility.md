---
title: 追跡プロファイルの展開ユーティリティ |Microsoft Docs
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
ms.openlocfilehash: cf72709c0527b9bc39b238be6d2ca98b698530fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313806"
---
# <a name="tracking-profile-deployment-utility"></a>追跡プロファイルの展開ユーティリティ
開発者は、bttdeploy ユーティリティを使用する追跡プロファイルを適用し、BAM インフラストラクチャから削除できます。 Bttdeploy ユーティリティを使用しては、機能的には追跡プロファイル エディター (TPE) で追跡プロファイルの適用 メニュー オプションをクリックします。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
 **使用方法**  
  
 **bttdeploy.exe [options] file name**  
  
|オプション|説明|  
|------------|-----------------|  
|/h または/でしょうか。|省略可能:Bttdeploy の構文を表示します。|  
|/mgdb \<server name[,port]\>\\<database name\>|省略可能:管理サーバー、ポート、およびプロファイルの適用先となるデータベースの名前を指定します。 **注:** このパラメーターを使用する場合、ポートは省略可能です。|  
|/remove と入力し|省略可能:追跡プロファイルを BAM データベースから削除することを指定します。|  
|filename|追跡の名前はプロファイルを適用または削除するファイルです。|  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)   
 [孤立した追跡プロファイルを削除する方法](../core/how-to-remove-orphaned-tracking-profiles.md)
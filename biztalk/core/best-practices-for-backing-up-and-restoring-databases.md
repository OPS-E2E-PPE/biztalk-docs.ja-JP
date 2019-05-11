---
title: バックアップおよびデータベースを復元するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ac2784a19a55d477f71c9b6542b7d46948d63f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529132"
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a>バックアップおよびデータベースを復元するためのベスト プラクティス
バックアップし、BizTalk Server データベースを復元できるように、次のベスト プラクティスを確認します。  
  
-   **バックアップの作成し復元のストラテジし、それらをテストします。**  
  
     適切なプランでは、ハードウェア障害により失われた場合にデータをすばやく回復できます。  
  
-   **ディスク領域を管理し、以前のバックアップ ファイルをアーカイブします。**  
  
     BizTalk Server のバックアップ ジョブでは、ディスク領域を節約するために、これらのバックアップ ファイルを管理する必要があるために、期限切れのバックアップ ファイルは削除されません。 データベースの新しい完全バックアップを作成すると、期限切れのバックアップ ファイルをプライマリ ディスク上の領域を解放するアーカイブ ストレージ デバイスを移動する必要があります。  
  
-   **同じコンピューターまたはバックアップするにはディスク上のバックアップを格納しないでください。**  
  
     元のデータを使用するコンピューターとは異なる、バックアップのコンピューターまたはディスクを指定する必要があります。 それ以外の場合、失われますすべてのデータ、ハードウェアが失敗した場合。  
  
-   **コピーを保持します。**  
  
     メディアの少なくとも 3 つのコピーを保持します。 適切に管理された環境に少なくとも 1 つのコピーをオフサイトをしてください。  
  
-   **試験的な復元を実行します。**  
  
     ファイルが正しくバックアップすることを確認するには、1 か月に 1 回以上の復元を試用版を実行します。 試用版の復元、ソフトウェアが正しく機能していることを確認するときを表示しないハードウェアの問題を発見します。 ハード ディスク失敗するかどうか、システムおよびデータベースを復元することを確認するまでは待機しません。  
  
-   **デバイスとメディアを保護します。**  
  
     記憶域デバイスとバックアップ メディアの両方をセキュリティで保護します。 他のユーザーが管理者を別のサーバーにデータを復元することによって盗まれた媒体からデータにアクセスすることができます。  
  
-   **バックアップを監視し、プロセスを復元します。**  
  
     バックアップすることを確認し、復元処理が成功した、バックアップし、BizTalk Server を復元するために使用する SQL Server エージェント ジョブを監視する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
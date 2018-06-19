---
title: バックアップおよびデータベースを復元するためのベスト プラクティス |Microsoft ドキュメント
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
ms.openlocfilehash: 2543f09c5118e58bd18ea2add113811fb733d884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231178"
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a>データベースのバックアップと復元のベスト プラクティス
BizTalk Server データベースのバックアップおよび復元を確実に行うことができるように、次のベスト プラクティスを参照してください。  
  
-   **バックアップの作成し復元戦略およびそれらをテストします。**  
  
     適切なプランを作成することにより、ハードウェアの障害が発生してデータが失われても、データを迅速に復元できます。  
  
-   **ディスク領域を管理し、以前のバックアップ ファイルを保存します。**  
  
     BizTalk Server のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを管理する必要があります。 データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。  
  
-   **同じコンピューターまたはディスクをバックアップするには、バックアップを格納しないでください。**  
  
     バックアップ用のコンピューターまたはディスクには、元のデータのある場所とは別のコンピューターを指定してください。 そうしないと、ハードウェアの障害が発生した場合にすべてのデータが失われる可能性があります。  
  
-   **コピーを保持します。**  
  
     メディアのコピーを 3 つ以上保持してください。 1 つ以上のコピーをオフサイトの適切に管理された環境で保管します。  
  
-   **テスト復元を実行します。**  
  
     テスト復元を少なくとも月に 1 度は実行し、ファイルが適切にバックアップされたことを確認してください。 テスト復元により、ソフトウェアが適性に動作しているかについて検証しても発見できないハードウェアの問題が明らかになります。 ハード ディスクの障害が発生する前に、システムおよびデータベースを復元できるかどうかを確認してください。  
  
-   **デバイスとメディアを保護します。**  
  
     ストレージ デバイスおよびバックアップ メディアの両方をセキュリティで保護します。 メディアを盗んだ人間は、自分が管理者となっているサーバーでメディアのデータを復元することによりデータにアクセスできます。  
  
-   **バックアップを監視し、プロセスを復元します。**  
  
     バックアップおよび復元のプロセスが正常に実行されたかどうかを確認するには、BizTalk Server のバックアップおよび復元に使用する SQL Server エージェント ジョブを監視する必要があります。  
  
## <a name="see-also"></a>参照  
 [バックアップと、BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
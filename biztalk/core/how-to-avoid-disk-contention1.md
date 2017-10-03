---
title: "ディスク Contention1 を回避する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702665046dbaee77412675e4be0edc602dd9e7e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a>ディスクの競合を防止する方法
BizTalk Server は永続的なシステムとして設計されているため、高スループットのシナリオではメッセージ ボックスで深刻な競合が発生する可能性があります。 ディスクが遅い場合には事態がさらに悪化します。 ディスクが遅い (ディスク アイドル時間の割合が低い) と、SQL がロックを保持する時間が長くなります (ロック待機時間とロック タイムアウトの値が大きくなる)。そうなると、メッセージ ボックス テーブル (スプールとアプリケーション キュー) のサイズが増加して、データベースの肥大化と制限を引き起こし、最終的には全体の維持可能なスループットが低下します。  
  
 ディスクの競合を防止するための推奨事項を以下に示します。  
  
-   高速な (マルチ スピンドルの) ディスクを使用する。  
  
-   可能であれば、高速な SAN にデータベースを展開する。 複数のデータベースが同じディスクを共有している場合は、それぞれ専用のディスクで構成することをお勧めします。 さらに、メッセージ ボックス データベースの MDF ファイルと LDF ファイルを別々のディスクに分けることをお勧めします。  
  
-   SQL で CPU が不足している場合は、メッセージ ボックス データベースを追跡データベースとは別の専用のサーバーに分離することを検討してください。  
  
-   メッセージ ボックス データベースの専用のサーバーをセットアップした後は、CPU のアップグレードや、複数の CPU の追加によるスケール アップを検討してください。 MSDTC のログは、ローカル ドライブ (C:\WINDOWS\system32\Msdtc) に保存されるため、SQL Server のローカル ドライブを監視します。  
  
-   ページファイルや MSDTC のログによってローカル ドライブで競合が発生する場合は、ページファイルや MSDTC のログを別のドライブに移してみてください。
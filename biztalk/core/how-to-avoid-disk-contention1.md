---
title: ディスク Contention1 を回避する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9204fc727339a5fbab31cdf54bc8de488e588dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342670"
---
# <a name="how-to-avoid-disk-contention"></a>ディスクの競合を防止する方法
BizTalk Server は、高スループットのシナリオで、メッセージ ボックスできます競合が発生する重大な永続的なシステムとして設計されています。 ディスクが遅い場合には事態がさらに悪化します。 ディスクが低速 (低 % Disk Idle Time) の場合は、この可能性がありますロック長くなります (ロック待機時間と高のロック タイムアウト数) に増加し、メッセージ ボックス テーブル (スプールとアプリケーション キュー) が発生することができますを保持する SQL データベースの肥大と最終的な調整全体的な持続可能なスループットが低下なります。  
  
 ディスクの競合を回避するために、次を行うことをお勧めします。  
  
-   高速 (マルチ スピンドル) ディスクを使用します。  
  
-   可能であれば、高速な SAN 上のデータベースをデプロイします。 複数のデータベースが同じディスクを共有している場合は、それらを個別の専用ディスクを構成することをお勧めします。 さらに別のディスク上にメッセージ ボックス データベースの MDF および LDF ファイルを分離することをお勧めします。  
  
-   CPU、SQL が不足している場合は、追跡データベースから分離された専用のサーバーにメッセージ ボックス データベースを分離することを検討してください。  
  
-   メッセージ ボックス データベースに専用のサーバーを設定した後は、CPU のアップグレードやより多くの CPU の追加によるスケール アップを検討してください。 MSDTC のログはローカル ドライブ (C:\WINDOWS\system32\Msdtc) に保存されるため、SQL Server のローカル ドライブを監視します。  
  
-   ページファイルや MSDTC のログによってローカル ドライブで競合が発生する場合は、ページファイルや MSDTC のログを別のドライブに移してみてください。
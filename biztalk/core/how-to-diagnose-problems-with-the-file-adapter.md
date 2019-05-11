---
title: ファイル アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017d9f2027a42bb804b6baf4b2a14915e4a525de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385222"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a>ファイル アダプターに関する問題の診断方法
このセクションには、ファイル アダプターに関する問題の診断に役立つことができますの手順が含まれています。  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a>ファイル受信アダプターまたはファイル送信アダプターを使用して発生したエラーを診断する FileMon ユーティリティを実行します。  
  
1.  FileMon ユーティリティをダウンロード[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)します。  
  
2.  読み取るか、ファイル アダプターによって書き込まれる、または共有にフォルダーをホストするサーバー上のユーティリティがされている Filemon をインストールします。  
  
3.  Filemon ユーティリティを起動し、BizTalk ホスト インスタンス (BTSNTSvc.exe など) で、ファイル アダプターのハンドラーが実行されているによるファイル アクセスのみを監視するフィルターを適用します。  
  
4.  問題の原因となったシナリオを実行します。  
  
5.  ファイルの Filemon ユーティリティの監視を無効にし、生成されたログ ファイルをディスクに保存します。  
  
6.  生成されたログ ファイルで、エラーを確認します。  
  
    > [!NOTE]
    >  FileMon は、Microsoft ではサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [ファイル アダプターのトラブルシューティング](../core/troubleshooting-the-file-adapter.md)
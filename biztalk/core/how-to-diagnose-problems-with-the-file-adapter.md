---
title: "ファイル アダプターに関する問題を診断する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0481a3abdf497c093a87d7d74ea0356c7cad0d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a>ファイル アダプターに関する問題の診断方法
ここでは、ファイル アダプターに関する問題の診断手順について説明します。  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a>ファイル受信アダプターまたはファイル送信アダプターを使用したときに発生するエラーを診断するため、FileMon ユーティリティを実行する  
  
1.  FileMon ユーティリティをダウンロード[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)です。  
  
2.  ファイル アダプターの読み書き対象フォルダーまたは共有をホストするサーバー上に、Filemon ユーティリティをインストールします。  
  
3.  Filemon ユーティリティを起動し、フィルターを適用して、ファイル アダプターのハンドラーが実行されている BizTalk ホスト インスタンス (BTSNTSvc.exe など) でのファイル アクセスのみを監視するようにします。  
  
4.  問題を発生させるシナリオを再現します。  
  
5.  Filemon ユーティリティのファイル監視を無効にし、生成されたログ ファイルをディスクに保存します。  
  
6.  生成されたログ ファイルで、エラーを確認します。  
  
    > [!NOTE]
    >  Microsoft では FileMon をサポートしておらず、このプログラムの適合性に関して保証しません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [ファイル アダプターのトラブルシューティング](../core/troubleshooting-the-file-adapter.md)
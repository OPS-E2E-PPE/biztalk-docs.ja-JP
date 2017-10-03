---
title: "FTP アダプターに関する問題を診断する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 499d23d3-b705-4527-9929-147be157e6b3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e66be2e498449b1cdcc70e05c6195ccd8e4395d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>FTP アダプターに関する問題を診断する方法
ここでは、FTP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>FTP サーバーの FTP ログ ファイルでエラーの有無を確認する  
  
-   ソースまたはターゲット FTP サーバーのログ ファイルは、FTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、Windows Server または Windows XP コンピューターの FTP ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\MSFTPSVC1\  
  
    > [!NOTE]
    >  *%Windir%* FTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>FTP 受信場所または送信ポートのログ記録を有効にする  
  
-   FTP を構成する受信場所または送信ポート、**ログ**フォルダーです。 FTP アダプターはこのフォルダーに詳細なログ記録情報を保存します。 **ログ**フォルダー オプションは、 **FTP トランスポートのプロパティ**FTP トランスポートの種類で、受信場所または送信ポートを構成するときに ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)
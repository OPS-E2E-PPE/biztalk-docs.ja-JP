---
title: FTP アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 499d23d3-b705-4527-9929-147be157e6b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28d920a7bdc61e98832fb6818f66182ab69acbf2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987219"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>FTP アダプターに関する問題を診断する方法
ここでは、FTP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>FTP サーバーの FTP ログ ファイルでエラーの有無を確認する  
  
- ソースまたはターゲット FTP サーバーのログ ファイルは、FTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、Windows Server または Windows XP コンピューターの FTP ログ ファイルは次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\MSFTPSVC1\  
  
  > [!NOTE]
  >  *%Windir%* は FTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>FTP 受信場所または送信ポートのログ記録を有効にする  
  
-   Ftp アダプターは構成の受信場所または送信ポートを**ログ**フォルダー。 FTP アダプターはこのフォルダーに詳細なログ記録情報を保存します。 **ログ**フォルダー オプションは 使用可能な**FTP トランスポートのプロパティ**FTP トランスポートの種類で、受信場所または送信ポートを構成するときに、ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)
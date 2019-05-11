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
ms.openlocfilehash: 1b7b090ee9d77754cb6ed3e1f1fb5d4ae4938658
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338458"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>FTP アダプターに関する問題を診断する方法
このセクションには、FTP アダプターに関する問題の診断に役立つことができますの手順が含まれています。  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>FTP ログ ファイルを FTP サーバー上にエラーを確認してください。  
  
- ソースまたはターゲット FTP サーバーのログ ファイルは、FTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、Windows Server または Windows XP コンピューター上の FTP ログ ファイルは次のディレクトリにあります。  
  
   <em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\  
  
  > [!NOTE]
  >  *%Windir%* は FTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>FTP 受信場所または送信ポートのログ記録を有効にします。  
  
-   Ftp アダプターは構成の受信場所または送信ポートを**ログ**フォルダー。 FTP アダプターでは、詳細なログ情報をこのフォルダーに保存します。 **ログ**フォルダー オプションは 使用可能な**FTP トランスポートのプロパティ**FTP トランスポートの種類で、受信場所または送信ポートを構成するときに、ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)
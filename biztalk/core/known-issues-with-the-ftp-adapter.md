---
title: FTP アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e58f2db-9ec5-41fe-af02-9a7d60a217db
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcab9b35759d491c0732cfb2613a2fd4fe992a3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022488"
---
# <a name="known-issues-with-the-ftp-adapter"></a>FTP アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a>BizTalk Server で FTP アダプターを使用してデータを受信すると、データが重複または損失する場合がある  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で FTP アダプターを使用してデータを受信すると、データの重複または損失が発生します。  
  
##### <a name="cause"></a>原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプターは、指定された FTP サーバーを FTP クライアント プロトコルを使用してポーリングし、サーバーからデータを "そのまま" の状態で取得します。 FTP アダプターは、取得するデータを検証しません。 FTP アダプターは、取得したドキュメントを処理のため BizTalk メッセージング エンジンに送信した後、FTP サーバーから元のドキュメントを削除します。 FTP アダプターが、ホスト アプリケーションが書き込み中のドキュメントを FTP サーバーから取得すると、取得したドキュメントは不完全になります。 元のドキュメントの不完全なコピーを取得した場合、次のシナリオでデータの重複やデータの損失が発生することがあります。  
  
-   元のドキュメントがホスト アプリケーションから FTP サーバーに書き込まれている最中の場合、FTP アダプターはそのドキュメントを削除できないので、受信場所に構成された次のポーリング間隔でそのドキュメントのコピーをもう 1 つ取得します。 この動作により、ドキュメントの重複が発生します。  
  
-   ホスト アプリケーションから FTP サーバーへのドキュメントの書き込みが完了すると、そのドキュメントは削除されます。 この動作により、データの損失が発生します。  
  
##### <a name="resolution"></a>解決策  
 この動作を回避するには、以下のいずれかの方法を使用します。  
  
- パブリック FTP フォルダーと同じハード ディスク上の一時フォルダーに書き込み、一時フォルダーの内容を定期的に FTP フォルダーに移動するように、ホスト アプリケーションを構成します。 移動操作がアトミックになるように、一時フォルダーを、パブリック FTP フォルダーと同じハード ディスク上に配置する必要があります。 アトミック操作とは、機能的にそれ以上分割できない操作のことです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプターを使用してデータをパブリック FTP フォルダーに書き込む場合、この操作を行うには、送信ポートの構成時に [FTP トランスポートのプロパティ] ダイアログ ボックスで "一時フォルダー" プロパティを指定します。 "一時フォルダー" プロパティを指定する場合は、このフォルダーがパブリック FTP フォルダーと同じ物理ディスク上にあることを確認します。  
  
- ホスト アプリケーションがデータを FTP サーバーに書き込まない場合、サービス時間帯に動作するように FTP 受信場所を構成します。 サービス時間帯は、受信場所のプロパティを構成する際に指定できます。  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a>FTP アダプターではサーバー証明書の失効の確認をサポートしていない  
  
##### <a name="problem"></a>問題  
 BizTalk Server で FTP アダプターが拡張され、SSL や TLS を使用して、FTPS サーバーとの間にセキュリティで保護されたファイル転送をサポートします。 証明書失効リスト (CRL) には失効し、無効になった証明書のリストが入っています。 FTP アダプターでは、サーバー証明書を認証するために CRL を参照しません。  
  
##### <a name="cause"></a>原因  
 仕様上、FTP アダプターではサーバー証明書を受け取る前に CRL を参照しません。  
  
##### <a name="resolution"></a>解決策  
 操作は不要です。この動作は仕様です。  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a>FTP アダプターで最大ファイル サイズを超えるファイルがダウンロードされる  
  
##### <a name="problem"></a>問題  
 FTP 受信アダプターでは、指定した最大ファイル サイズ プロパティを超えるサイズのファイルが次の FTP サーバーからダウンロードされます。  
  
-   AIX  
  
-   MVS  
  
-   AS400  
  
-   GXS  
  
##### <a name="cause"></a>原因  
 仕様上、FTP アダプターでは上記の FTP サーバーからファイルをダウンロードするとき、最大ファイル サイズの設定に従いません。  
  
##### <a name="resolution"></a>解決策  
 操作は不要です。この動作は仕様です。  
  
## <a name="see-also"></a>参照  
 [FTP 受信場所を構成する方法](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3)   
 [FTP アダプターのトラブルシューティング](../core/troubleshooting-the-ftp-adapter.md)
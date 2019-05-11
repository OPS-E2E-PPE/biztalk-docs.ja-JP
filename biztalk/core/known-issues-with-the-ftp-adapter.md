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
ms.openlocfilehash: 682e87e2cfca4906b0f9c582d5e33a235525e293
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329108"
---
# <a name="known-issues-with-the-ftp-adapter"></a>FTP アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a>データを複製または BizTalk Server で FTP アダプターを使用してデータを受信するときに失われる可能性があります。  
  
##### <a name="problem"></a>問題  
 データの重複またはデータを受信するときに失われる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]FTP アダプターを使用します。  
  
##### <a name="cause"></a>原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプター、FTP クライアント プロトコルを使用して、指定された FTP サーバーをポーリングおよび"です。」と、サーバーからデータを取得します。 FTP アダプターでは、取得したデータは検証されません。 FTP アダプターが、BizTalk メッセージング エンジンで処理するために取得したドキュメントを送信し、元のドキュメント、FTP サーバーから削除します。 FTP アダプターは、ホスト アプリケーションによってにまだ書き込まれている FTP サーバーからドキュメントを取得する場合、取得したドキュメントは完了できません。 FTP アダプターは、元のドキュメントの不完全なコピーを取得する場合、次のシナリオでデータの重複やデータの損失は発生します。  
  
-   場合は、元のドキュメントは、ホスト アプリケーションによって FTP サーバーにまだ書き込まれるは、FTP アダプター、ドキュメントを削除することはできず、次のポーリング間隔で構成されている受信場所のドキュメントの別のコピーを取得します。 この動作により、ドキュメントの重複が発生します。  
  
-   ホスト アプリケーションが FTP サーバーへのドキュメントの書き込みを終了すると、ドキュメントが削除されます。 この動作には、発生するデータの損失が発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を回避するには、次のメソッドのいずれかを使用します。  
  
- パブリック FTP フォルダーと同じハード_ディスク上の一時フォルダーに書き込むと、定期的に一時フォルダーの内容を FTP フォルダーに移動するホスト アプリケーションを構成します。 一時フォルダーは、移動操作がアトミックであることを確認するパブリック FTP フォルダーと同じハード_ディスクになければなりません。 分割不可能な操作は、機能的割り切れない操作です。 使用して、パブリック FTP フォルダーにデータを記述するかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP アダプターでは、これを行う送信ポートを構成するときに、FTP トランスポートのプロパティ ダイアログ ボックスの一時フォルダのプロパティを指定しています。 一時フォルダーのプロパティを指定する場合は、このフォルダーがパブリック FTP フォルダーと同じ物理ディスクにあることを確認してください。  
  
- 構成、FTP 受信場所でホスト アプリケーションが FTP サーバーへのデータを書き込んでいないときに、サービス時間帯内で動作します。 受信場所のプロパティを構成するときに、サービス時間帯を指定できます。  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a>FTP アダプターがサーバー証明書の失効の確認をサポートしていません  
  
##### <a name="problem"></a>問題  
 BizTalk Server で FTP アダプターが拡張され、SSL や TLS を使用して、FTPS サーバーとの間にセキュリティで保護されたファイル転送をサポートします。 証明書失効リスト (CRL) には、失効し、無効になっている証明書の一覧が含まれています。 FTP アダプターでは、サーバー証明書を認証するため、CRL は参照しません。  
  
##### <a name="cause"></a>原因  
 仕様上、FTP アダプターは、サーバー証明書を受け入れる前に CRL を参照しません。  
  
##### <a name="resolution"></a>解決策  
 操作は不要です。この動作は仕様です。  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a>FTP アダプターがファイルの最大サイズより大きいファイルをダウンロードします。  
  
##### <a name="problem"></a>問題  
 FTP は、アダプターのダウンロード ファイルのサイズが次の FTP サーバーから指定した最大ファイル サイズ プロパティよりも大きいが表示されます。  
  
-   AIX  
  
-   MVS  
  
-   AS400  
  
-   GXS  
  
##### <a name="cause"></a>原因  
 仕様では、FTP アダプターはファイルの最大サイズを考慮しないこれらの FTP サーバーからファイルをダウンロードするときに。  
  
##### <a name="resolution"></a>解決策  
 操作は不要です。この動作は仕様です。  
  
## <a name="see-also"></a>参照  
 [FTP 受信場所を構成する方法](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3)   
 [FTP アダプターのトラブルシューティング](../core/troubleshooting-the-ftp-adapter.md)
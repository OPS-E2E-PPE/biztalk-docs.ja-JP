---
title: クラスター化された Host1 でアダプター ハンドラーの実行に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- receive adapters, clustering
- clustering, POP3 adapters
- FTP adapters, clustering
- clustering, receive adapters
- NLB system
- MSMQ send handler
- MSMQ receive handler
- clustering, FTP adapters
- handlers [adapters], best practices
- hosts, clustering
- MSMQ adapters
- clustering, MSMQ adapters
- adapters, best practices
- adapters, handlers
- POP3 adapters, clustering
- MSMQ adapters, clustering
- clustering
ms.assetid: ee66663c-4f4d-4515-9df1-aacf4fc72be4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00436ad42634c2672560499c891ada33547f0342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977035"
---
# <a name="considerations-for-running-adapter-handlers-within-a-clustered-host"></a>クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点
BizTalk ホストのクラスター サポートを利用すると、統合された BizTalk アダプター (FTP アダプター、SFTP アダプター、MSMQ アダプター、および POP3 アダプター) に対して高可用性を実現できます。 また、順次配送の目的でアダプターの単一インスタンスを実行する場合に、ホスト クラスター サポートを利用して高い可用性を実現できます。  
  
 すべての BizTalk アダプター ハンドラーは、クラスター化されたホストで実行できます。ただし、クラスター化されたホストでアダプター ハンドラーを実行しても、次に説明する以外のメリットはありません。 処理の要件では、次に示すシナリオのいずれかが含まれない場合、クラスター化されたホストでアダプター ハンドラーいない実行する必要があります。  
  
## <a name="running-the-ftp-or-sftp-adapter-receive-handler-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで FTP または SFTP アダプターの受信ハンドラーを実行する  
 BizTalk Server の統合されたアダプターのほとんどは、複数のアダプター ハンドラーを作成し、BizTalk グループ内の複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上にある BizTalk ホスト インスタンスで実行することで、高い可用性を実現できます。 ただし、複数の BizTalk ホスト インスタンスで FTP または SFTP アダプターの受信ハンドラーが同時に実行されないように構成しておく必要があります。 その理由は、FTP または SFTP 受信アダプターが FTP または SFTP プロトコルを通じて対象システムからファイルを取得するためです。 FTP または SFTP プロトコルでは、FTP または SFTP 受信アダプターの複数インスタンスを実行した場合、同一ファイルの複数コピーが同時に取得されないようにするためのファイルのロックが行われません。  
  
 FTP または SFTP 受信アダプターの高可用性を実現するには、クラスター化された BizTalk ホスト インスタンスで実行されるように FTP または SFTP 受信アダプターを構成する必要があります。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーを実行する  
 MSMQ アダプターの高可用性を確保し、MSMQ アダプターによって送受信されるメッセージのトランザクションの一貫性を保つには、次の設定を行ってください。  
  
1. Windows クラスタ グループでクラスター化リソースとしてのメッセージ キュー (MSMQ) を構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
2. クラスター化された MSMQ サービスを、クラスター化された BizTalk ホストのリソース依存関係リストに追加します。 これにより、常にクラスター化された BizTalk ホストのフェールオーバーのシナリオでクラスター化された MSMQ サービスの後に開始されます。  
  
3. クラスター化された MSMQ リソースと同じクラスター グループ内のクラスター リソースとして構成されている BizTalk ホスト インスタンスで、MSMQ アダプターの送信ハンドラーおよび受信ハンドラーを構成します。  
  
   次の理由により、これらの手順が推奨されています。  
  
   **MSMQ アダプターの受信ハンドラー** – MSMQ 4.0 (Windows Server 2008) より前のバージョンの MSMQ はリモート トランザクション読み取りをサポートしていません。 ローカル トランザクションの読み込みはサポートされています。 この場合、MSMQ アダプターの受信ハンドラーは、MSMQ アダプターでローカル トランザクションの読み込みを完了するクラスター化されたメッセージ キュー サービスに対してローカルのホスト インスタンスで実行する必要があります。  
  
> [!IMPORTANT]
>  MSMQ アダプターの受信ハンドラーを実行するには、メッセージ キュー サービスのローカルのクラスター化されていないインスタンスが、受信ハンドラーのホスト インスタンスが実行されている同じコンピューター上で実行されている必要があります。  
  
 **MSMQ アダプターの送信ハンドラー** - できる場合は、MSMQ サービスを送信キューが失敗したように、MSMQ アダプター、MSMQ アダプターの送信ハンドラーで使用される発信キューによるトランザクション送信の一貫性を高可用性にする必要があります再開します。 クラスター グループでクラスター化されたメッセージ Queuingresource と MSMQ アダプター ハンドラーの構成と、MSMQ アダプターの送信ハンドラーで使用される発信キューを高可用性になることが確認します。 これにより、メッセージ キュー サービスが失敗した場合にメッセージが失われる可能性が軽減されます。  
  
> [!NOTE]
>  MSMQ 受信場所が**のみ**BizTalk グループに複数の BizTalk コンピューター上のホストが表示される、MSMQ を実行して高可用性を実現することができますし、リモートの MSMQ サーバー上の MSMQ キューから受信します。  MSMQ の高可用性を実現するには、リモート MSMQ サーバーが Windows でフェールオーバー クラスタ リングを使用することを確認する必要があります。  トランザクション キューを使用して場合リモート MSMQ サーバーが MSMQ 4.0 (Windows Server 2008) を実行する必要がありますまたはそれ以降。  
  
## <a name="running-the-pop3-adapter-receive-handler-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーを実行する  
 POP3 アダプターが読み込みを行う POP3 サーバーで同一のメールボックスに対する複数の同時接続が許可されている場合を除き、クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーが実行されるように構成する必要はありません。 POP3 アダプターが接続されている POP3 サーバーでメールボックスに対する複数の同時接続が許可されている場合は、単一の POP3 アダプター受信ハンドラーがクラスター化された BizTalk ホスト インスタンスで実行されるように構成して、POP3 アダプターの高可用性を維持することをお勧めします。 その理由は、POP3 受信アダプターの複数のインスタンスを実行した場合に、同じ電子メール メッセージの複数コピーが同時に取得される危険を回避するためです。  
  
## <a name="running-a-receive-adapter-that-supports-ordered-delivery-with-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで順次配送をサポートする受信アダプターを実行する  
 MSMQ および MQSeries の統合アダプターは、ドキュメントを受信した順番で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信する機能を提供します。 この機能を正しく実装するには、どの時点においても、これらの受信アダプターの単一インスタンスだけが実行されている必要があります。 これらのアダプターの単一インスタンスの高い可用性を実現するには、クラスター化された BizTalk ホスト インスタンスで実行されるようにアダプターを構成する必要があります。
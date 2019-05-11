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
ms.openlocfilehash: d6ac819e5255a423427e0e8c10235f73ab1ced5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390394"
---
# <a name="considerations-for-running-adapter-handlers-within-a-clustered-host"></a>クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項
BizTalk ホストのクラスターのサポートは、次の統合 BizTalk アダプターの高可用性を実現する使用可能な: FTP アダプター、SFTP アダプター、MSMQ アダプター、および POP3 アダプター。 また、順次配送の目的でアダプターの単一インスタンスを実行する場合に、ホスト クラスター サポートを利用して高い可用性を実現できます。  
  
 すべての BizTalk アダプター ハンドラーは、クラスター化されたホストで実行できますが、以下に示すように、以外のクラスター化されたホストでアダプター ハンドラーを実行するために派生の利点はありません。 処理の要件では、次に示すシナリオのいずれかが含まれない場合、クラスター化されたホストでアダプター ハンドラーいない実行する必要があります。  
  
## <a name="running-the-ftp-or-sftp-adapter-receive-handler-within-a-clustered-biztalk-host"></a>FTP または SFTP を実行しているアダプターの受信ハンドラーがクラスター化された BizTalk ホスト  
 ほとんどの BizTalk Server が BizTalk で実行する複数のアダプター ハンドラーを作成して、統合アダプター、高可用性を実現できます別のインスタンスをホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk グループ内のサーバー。 FTP または SFTP アダプターの受信ハンドラーは should not、ただし、複数の BizTalk ホスト インスタンスで同時に実行するように構成します。 FTP または SFTP 受信アダプターの使用は、ターゲット システムからファイルを取得する FTP または SFTP プロトコルであるために、この推奨事項が行われます。 FTP または SFTP プロトコルでは、同じファイルの複数のコピーが同時に取得がされないようにするファイルをロックしません受信アダプターが FTP または SFTP の複数のインスタンスを実行している場合。  
  
 高可用性の FTP または SFTP 受信アダプターでは、構成する必要がありますを実現するには、FTP または SFTP アダプターがクラスター化された BizTalk ホスト インスタンスで実行するに受信します。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーを実行する  
 MSMQ アダプターの高可用性を確保して、MSMQ アダプターによって送受信されるメッセージのトランザクションの一貫性を確保するには、次の操作を行う必要があります。  
  
1. Windows クラスタ グループでクラスター化リソースとしてのメッセージ キュー (MSMQ) を構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
2. リソースの依存関係の一覧にクラスター化された BizTalk ホストのクラスター化された MSMQ サービスを追加します。 これにより、常にクラスター化された BizTalk ホストのフェールオーバーのシナリオでクラスター化された MSMQ サービスの後に開始されます。  
  
3. MSMQ アダプターの送信を構成し、クラスター化された MSMQ リソースと同じクラスター グループ内のクラスター リソースとして構成されている BizTalk ホスト インスタンスでハンドラーを受信します。  
  
   次の手順は、次の理由から推奨されます。  
  
   **MSMQ アダプターの受信ハンドラー** – MSMQ 4.0 (Windows Server 2008) より前のバージョンの MSMQ はリモート トランザクション読み取りをサポートしていません。 ローカル トランザクションの読み込みはサポートされています。 この場合、MSMQ アダプターの受信ハンドラーは、MSMQ アダプターでローカル トランザクションの読み込みを完了するクラスター化されたメッセージ キュー サービスに対してローカルのホスト インスタンスで実行する必要があります。  
  
> [!IMPORTANT]
>  MSMQ アダプターの受信ハンドラーでは、受信ハンドラーのホスト インスタンスがで実行されている同じコンピューター上のメッセージ キュー サービスはローカルの非クラスター化インスタンスが実行されていることが必要です。  
  
 **MSMQ アダプターの送信ハンドラー** - できる場合は、MSMQ サービスを送信キューが失敗したように、MSMQ アダプター、MSMQ アダプターの送信ハンドラーで使用される発信キューによるトランザクション送信の一貫性を高可用性にする必要があります再開します。 クラスター グループでクラスター化されたメッセージ Queuingresource と MSMQ アダプター ハンドラーの構成と、MSMQ アダプターの送信ハンドラーで使用される発信キューを高可用性になることが確認します。 メッセージ キュー サービスが失敗したことは、メッセージの損失の可能性が軽減されます。  
  
> [!NOTE]
>  MSMQ 受信場所が**のみ**BizTalk グループに複数の BizTalk コンピューター上のホストが表示される、MSMQ を実行して高可用性を実現することができますし、リモートの MSMQ サーバー上の MSMQ キューから受信します。  MSMQ の高可用性を実現するには、リモート MSMQ サーバーが Windows でフェールオーバー クラスタ リングを使用することを確認する必要があります。  トランザクション キューを使用して場合リモート MSMQ サーバーが MSMQ 4.0 (Windows Server 2008) を実行する必要がありますまたはそれ以降。  
  
## <a name="running-the-pop3-adapter-receive-handler-within-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーを実行する  
 POP3 アダプターの受信ハンドラーは、アダプターが読み込みを行う POP3 サーバーが同一のメールボックスに対する複数の同時接続が許可されない限り、クラスター化された BizTalk ホストで実行するように構成する必要はありません。 受信ハンドラーを BizTalk ホストで実行するを単一の POP3 アダプターを構成することで、POP3 アダプターの可用性に POP3 アダプターが接続されている POP3 サーバーが高いことをお勧めします。 その後、メールボックスに対する複数の同時接続を許可している場合クラスター化されたインスタンス。 この推奨事項の同じ電子メール メッセージの複数のコピーが同時に取得がされないようにする受信アダプターが POP3 の複数のインスタンスを実行している場合。  
  
## <a name="running-a-receive-adapter-that-supports-ordered-delivery-with-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストで順次配送をサポートする受信アダプターを実行する  
 MSMQ および MQSeries 統合アダプターにドキュメントを送信する機能を提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信した順序で。 この機能を正しく実装では、これらのインスタンスが 1 つだけ受信アダプターである必要があります、特定の時点で実行されています。 これらのアダプターの 1 つのインスタンスの高可用性を実現するには、クラスター化された BizTalk ホスト インスタンスで実行するように構成する必要があります。
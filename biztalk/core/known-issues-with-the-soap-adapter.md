---
title: "SOAP アダプターに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 671510c6901fc399580ab73018e67eadc86f7212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-soap-adapter"></a>SOAP アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a>負荷状況下で SOAP アダプターのパフォーマンスが低下したりエラーが発生する  
  
##### <a name="problem"></a>問題  
 負荷状況下で SOAP アダプターのパフォーマンスが低下したりエラーが発生する  
  
##### <a name="cause"></a>原因  
 この問題は、SOAP アダプターまたは SOAP アダプターに影響する依存関係コンポーネントの既定の構成オプションが、負荷状況下のパフォーマンス用にチューニングされていないために発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題は解決するのには、SOAP アダプターまたはトピックで説明する依存関係コンポーネントの構成オプションを変更[構成パラメーターに影響を与えるアダプター パフォーマンス](../core/configuration-parameters-that-affect-adapter-performance.md)です。  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a>MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントが、SOAP アダプターで処理されたデータをエンコードまたはデコードできない  
  
##### <a name="problem"></a>問題  
 MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントが、SOAP アダプターで処理されたデータをエンコードまたはデコードできない  
  
##### <a name="cause"></a>原因  
 この問題は、SOAP アダプターが、処理のアダプター ステージにある SOAP メッセージをアセンブルおよび逆アセンブルするために発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、SSL (Secure Sockets Layer) による保護された通信を使って、SOAP アダプターが処理するメッセージをエンコードします。 送信側で使用して、**クライアント証明書の拇印**これを実現するには、SOAP アダプター プロパティ ページ内のプロパティです。 受信側では、SSL による保護された通信で BizTalk Web サービスをホストする仮想ディレクトリを構成する必要があります。  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a>SOAP アダプターをホストする既定の AppDomain がアンロードされてホスト プロセスがハングアップする  
  
##### <a name="problem"></a>問題  
 SOAP アダプターをホストするプロセスがハングアップし、それによってプロセス内のその他すべての Web サービスがハングアップします。 これによって次のエラーが発生するおそれがあります。  
  
 パイプライン"不明"を実行中にエラーが発生しました:「不明」のソース:"不明"受信ポート::"TwoWayLatencyLoopBack_RxPort"、URI:"/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx"理由: アンロードされた AppDomain にアクセスしようとしています。  
  
##### <a name="cause"></a>原因  
 SOAP アダプターは IIS プロセス領域で実行されます。 IIS AppPool に複数の Web サービスが存在する場合は、すべての Web サービスが独自の AppDomain を持つことになります。  
  
 既定ですべてのメッセージング エンジン オブジェクトが最初の AppDomain に作成されます (つまり、します。 AppDomain 最初の Web サービスに対応する)。 最初の Web サービスが何らかの理由で一定期間以上非アクティブになると、IIS は最初の AppDomain をアンロードします。 この場合、ホスティング プロセスのすべてのサービスが使用できなくなります。  
  
##### <a name="resolution"></a>解決策  
 AppDomain がアンロードされないようにするには、次の手順に従います。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**  をクリックし、 **BizTalk Server 管理コンソール**です。  
  
2.  **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**のプラットフォームの設定**、クリックして**ホスト**です。  
  
3.  ホストの一覧から、必要なホストを右クリックし、をクリックして**設定**です。  
  
4.  **BizTalk 設定ダッシュ ボード**、確認**分離アダプターの既定のアプリケーション ドメイン****全般**タブです。  
  
 この設定を行うと、BizTalk メッセージング エンジン オブジェクトが、独自の AppDomain ではなく既定の AppDomain に作成されます。 既定の AppDomain はアンロードされないため、問題は発生しなくなります。  
  
#### <a name="the-soap-adapter-fails-to-register"></a>SOAP アダプターを登録できない  
  
##### <a name="problem"></a>問題  
 BizTalk Server が SOAP (または HTTP) アダプターを登録する際に次のエラーが発生することがあります。  
  
 "メッセージング エンジンがアダプター "SOAP" を登録できませんでした。 詳細:"同一プロセス内の複数のアダプター型の登録がないシナリオをサポートします。 たとえば、HTTP および SOAP の受信アダプターは同じプロセス内に共存できません。"  
  
 または  
  
 "メッセージング エンジンがアダプター "HTTP" を登録できませんでした。 詳細:"同一プロセス内の複数のアダプター型の登録がないシナリオをサポートします。  たとえば、HTTP および SOAP の受信アダプターは同じプロセス内に共存できません。"  
  
##### <a name="cause"></a>原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 上の IIS 6.x で実行する場合は、SOAP アダプターと HTTP アダプターを同じプロセス領域またはアプリケーション プールで実行できません。  
  
##### <a name="resolution"></a>解決策  
 SOAP アダプターと HTTP アダプターの両方を同じ Web サーバーで使用する必要があるインストール環境では、各アダプターに別個のアプリケーション プールを作成する必要があります。  作成された各アプリケーション プールには、各アダプターの仮想ディレクトリがそれぞれ割り当てられます。  
  
> [!NOTE]
>  Windows XP では、IIS 5.x の下で SOAP アダプターと HTTP アダプターが別々のプロセス領域で実行されるため、この問題は発生しません。  SOAP アダプターは aspnet_wp.exe プロセスで ASP.Net アプリケーションとして実行されます。  HTTP アダプターは、dllhost.exe の専用のプロセス領域で実行されます。  このため両方のアダプターが分離されて、同じ Web サーバーで同時に実行できるようになります。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターのトラブルシューティング](../core/troubleshooting-the-soap-adapter.md)
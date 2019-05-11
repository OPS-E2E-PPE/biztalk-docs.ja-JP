---
title: SOAP アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0d27f01efee12e32d201a1a0f7ab9e686088cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329019"
---
# <a name="known-issues-with-the-soap-adapter"></a>SOAP アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a>SOAP アダプターのパフォーマンスの低下が発生したまたは負荷の下でエラーが生成されます。  
  
##### <a name="problem"></a>問題  
 SOAP アダプターのパフォーマンスの低下が発生したまたは負荷の下でエラーが生成されます。  
  
##### <a name="cause"></a>原因  
 SOAP アダプターまたは SOAP アダプターに影響する依存関係コンポーネントの既定の構成オプションが負荷の下でパフォーマンスのチューニングされないために、この問題が発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、変更の SOAP アダプターまたはトピックで説明されている依存関係コンポーネントの構成オプション[構成パラメーターを アダプターのパフォーマンスの影響を与える](../core/configuration-parameters-that-affect-adapter-performance.md)します。  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a>MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントをエンコードおよび SOAP アダプターで処理されるデータをデコードできません。  
  
##### <a name="problem"></a>問題  
 MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントをエンコードおよび SOAP アダプターで処理されるデータをデコードできません。  
  
##### <a name="cause"></a>原因  
 この問題は、SOAP アダプターをアセンブルし、プロセスのアダプター ステージでは、SOAP メッセージを逆アセンブルするために発生します。  
  
##### <a name="resolution"></a>解決策  
 セキュリティで保護されたソケット レイヤー (SSL を使用)、SOAP アダプタによって処理されるメッセージをエンコードする通信をセキュリティで保護する、この問題を解決します。 送信側を使用して、**クライアント証明書の拇印**でこれを実現するには、SOAP アダプター プロパティ ページのプロパティ。 受信側で安全な通信を SSL 用の BizTalk Web サービスをホストする仮想ディレクトリを構成する必要があります。  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a>既定の SOAP アダプターをホストする AppDomain はホスト プロセスがハングアップするアンロードされて取得します。  
  
##### <a name="problem"></a>問題  
 プロセスがハングアップするその他のすべての Web サービスを原因と、SOAP アダプターをホストするプロセスがハングします。 次のエラーがあります。  
  
 パイプライン"不明"を実行中にエラーが発生しました。「不明」のソース:「不明」の受信ポート。"TwoWayLatencyLoopBack_RxPort"、URI:"/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx"理由。アンロードされた AppDomain にアクセスしようとしています。  
  
##### <a name="cause"></a>原因  
 SOAP アダプターは、IIS プロセス領域で実行されます。 IIS AppPool に複数の Web サービスが存在する場合は、独自の AppDomain を持つのすべての Web サービスが終了します。  
  
 既定ですべてのメッセージング エンジン オブジェクトが最初の AppDomain で作成されます (つまり、します。 AppDomain 最初の Web サービスに対応する)。 最初の Web サービスが何らかの理由の長期間非アクティブ、IIS は最初の AppDomain をアンロードします。 この場合、すべてのサービス ホスト プロセスでは使用できなくなります。  
  
##### <a name="resolution"></a>解決策  
 AppDomain がアンロードされないようにするには、次の手順に従います。  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**順にクリックします**BizTalk Server 管理**します。  
  
2. **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**ホスト**します。  
  
3. ホストの一覧から、必要なホストを右クリックし、**設定**します。  
  
4. **BizTalk 設定ダッシュ ボード**、確認**分離アダプターの既定のアプリケーション ドメイン****全般**タブ。  
  
   これを行うときに、BizTalk メッセージング エンジン オブジェクトは、既定値の代わりに、独自の Appdomain での AppDomain に作成されます。 既定の AppDomain はアンロードされないため、問題は発生しません。  
  
#### <a name="the-soap-adapter-fails-to-register"></a>SOAP アダプターを登録できません。  
  
##### <a name="problem"></a>問題  
 BizTalk Server が SOAP (または HTTP) アダプターを登録しようとした場合、次のエラーが発生します。  
  
 "メッセージング エンジンがアダプター"SOAP"を登録できませんでした。 詳細:"同じプロセス内で複数のアダプターの種類を登録するシナリオ サポートされていません。 たとえば HTTP および SOAP 受信アダプター共存できません同じプロセス内で"。  
  
 または  
  
 "メッセージング エンジンがアダプター"HTTP"を登録できませんでした。 詳細:"同じプロセス内で複数のアダプターの種類を登録するシナリオ サポートされていません。  たとえば HTTP および SOAP 受信アダプター共存できません同じプロセス内で"。  
  
##### <a name="cause"></a>原因  
 実行時に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]/IIS 6.x、SOAP および HTTP アダプターは同じプロセス領域またはアプリケーション プールで実行することはできません。  
  
##### <a name="resolution"></a>解決策  
 同じ Web サーバーでは SOAP および HTTP アダプターを使用して、インストールが必要な場合、アダプターごとに個別のアプリケーション プールを作成する必要があります。  作成されると、各アダプター用の仮想ディレクトリごとに割り当てられている別のアプリケーション プール。  
  
> [!NOTE]
>  この問題は発生しません以降の Windows XP でこれらのオペレーティング システムで IIS 下で別のプロセス領域で実行する SOAP と HTTP アダプター 5.x します。  SOAP アダプターは aspnet_wp.exe プロセスで ASP.Net アプリケーションとして実行されます。  HTTP アダプターは、dllhost.exe の専用のプロセス領域で実行されます。  そのため両方のアダプターは、同じ Web サーバーに同時に実行できるように、互いから分離されます。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターのトラブルシューティング](../core/troubleshooting-the-soap-adapter.md)
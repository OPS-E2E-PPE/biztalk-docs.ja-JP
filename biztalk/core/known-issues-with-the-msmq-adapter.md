---
title: MSMQ アダプターに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce77cdac-79c1-4529-8f09-0fb1f87ca037
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f210d0e480a311aed0bed5d50f6a827bd6ea4e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22262618"
---
# <a name="known-issues-with-the-msmq-adapter"></a>MSMQ アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="msmq-adapter-receive-locations-do-not-process-documents"></a>MSMQ アダプターの受信場所でドキュメントが処理されない  
  
##### <a name="problem"></a>問題  
 MSMQ アダプターの受信場所でドキュメントが処理されません。  
  
##### <a name="cause"></a>原因  
 MSMQ アダプターの受信ハンドラーが実行されている BizTalk ホスト インスタンスに関連付けられた .NET スレッド プールで、使用できるスレッド数が不足している場合、MSMQ アダプターの受信場所ではドキュメントを処理できません。  
  
##### <a name="resolution"></a>解決策  
 ホスト インスタンスの .NET スレッド プールで使用可能なスレッドの数を増やすには、手順で、**ホスト用 CLR Hosting スレッド値**」の「[に影響するアダプターの構成パラメーターパフォーマンス](../core/configuration-parameters-that-affect-adapter-performance.md)です。  
  
 MSMQ 受信ハンドラーにバインドされている各 MSMQ 受信場所は、.NET スレッド プールからスレッドを必要とするため、設定 **MinIOThreads** と **MinWorkerThreads** には、MSMQ の数より大きい値には、受信場所の受信ハンドラーにバインドします。 したがっての値を設定 **MaxIOThreads** と **MaxWorkerThreads** MSMQ の数と同じ値には、受信場所の受信ハンドラーにバインドされている * ヘッドルームを許可するように 2。  
  
|DWORD エントリ|推奨値|  
|-----------------|-----------------------|  
|MaxIOThreads|MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数 * 2。|  
|MaxWorkerThreads|MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数 * 2。|  
|MinIOThreads|MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数|  
|MinWorkerThreads|MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数|  
  
 これらの推奨値には、ホスト インスタンス内で実行されている他のアダプター ハンドラーやオーケストレーションによって使用されるスレッドは考慮されていません。したがって、これらのスレッドを考慮して値を増やす必要があります。  
  
#### <a name="msmq-adapter-receive-locations-shut-down-shortly-after-they-are-enabled"></a>有効にした MSMQ アダプターの受信場所がすぐにシャットダウンする  
  
##### <a name="problem"></a>問題  
 有効にした MSMQ 受信場所がすぐにシャットダウンします。  
  
##### <a name="cause"></a>原因  
 メッセージ キュー サービスのクラスター化されていないローカル インスタンスが、MSMQ 受信ハンドラーのホスト インスタンスと同じコンピューター上で実行されていない場合に、この問題が発生することがあります。  
  
##### <a name="resolution"></a>解決策  
 MSMQ 受信ハンドラーのホスト インスタンスを実行中のコンピューターで、メッセージ キュー サービスを開始します メッセージ キュー サービスのクラスター化されたインスタンスが、MSMQ アダプターの受信ハンドラーと同じコンピューター上で実行されている場合でも、メッセージ キュー サービスのローカル インスタンスが実行されている必要があります。  
  
#### <a name="sc-tool-causes-error-when-attempting-to-stop-service-for-host-instance"></a>SC ツールでホスト インスタンスのサービスを停止しようとしたときにエラーが発生する  
  
##### <a name="problem"></a>問題  
 SC ツール (Sc.exe) を使用して BizTalk ホスト インスタンスのサービスをシャットダウンしようとすると、次のようなエラー メッセージが表示される場合があります。  
  
 **ControlService FAILED 1053:**  
  
 **サービスは適時に開始または制御要求に応答しませんでした。**  
  
 このエラー メッセージが表示された後、BizTalk ホスト インスタンスのサービスが停止します。 しかし、SC ツールによってサービスがシャットダウンされるまで、2 分以上かかる場合があります。  
  
 Microsoft メッセージ キューの受信場所を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で有効にしたときに、この問題が発生します。  
  
 また、次のようなエラー メッセージがシステム ログに記録されることもあります。  
  
 **イベントの種類: エラー**  
  
 **イベント ソース: サービス コントロール マネージャー**  
  
 **イベント カテゴリ: なし**  
  
 **イベント ID: 7011**  
  
 **説明:**  
  
 **タイムアウト (30000 ミリ秒) BTSSvc$ BizTalkServerApplication サービスからトランザクションの応答を待機しています。**  
  
##### <a name="resolution"></a>解決策  
 サポートされている修正プログラムを Microsoft から入手できます。 ただし、この修正プログラムは、この資料で説明した問題のみの修正を目的としています。 この特定の問題が発生しているシステム以外には適用しないでください。 この修正プログラムは、さらにテストされる可能性があります。 したがって、この問題による影響が非常に深刻でない限り、この修正プログラムを含む次のサービス パックが提供されるまで待つことをお勧めします。  
  
 この問題を解決するには、マイクロソフト オンライン カスタマー サービスに要求を送信して、修正プログラムを入手してください。  
  
> [!NOTE]
>  さらに問題が発生した場合やトラブルシューティングが必要な場合、別のサービス要求の作成が必要になる場合があります。 この修正プログラムの対象とならない追加のサポートおよび問題には、通常のサポート費用が適用されます。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターのトラブルシューティング](../core/troubleshooting-the-msmq-adapter.md)
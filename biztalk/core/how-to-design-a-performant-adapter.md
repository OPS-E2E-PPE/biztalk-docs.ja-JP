---
title: パフォーマンスの高いアダプターを設計する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5a1f338-fd7c-41c8-a181-8da8b293c4cc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cffe98459213d04e0746ed2ec125c7e704684ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338495"
---
# <a name="how-to-design-a-performant-adapter"></a>パフォーマンスの高いアダプターを設計する方法
パフォーマンス向上のためのすべてのアダプターはメッセージのバッチを送信する、バッチの転送、および一般的にバッチのメッセージに対する操作の実行に関して、バッチに対応してください。 アダプターは、バッチまたはバッチでは、アダプターのデザイン時ユーザー インターフェイスから構成できるバイト数のサイズなど、構成可能なパフォーマンス関連の属性を公開しようとする必要があります。  
  
 前述のように、アダプターは、送信ホストのパフォーマンスの低下を避けるため、非ブロッキング送信を常に実行する必要がありますを送信します。 メッセージング エンジン Api をさらにブロックすることは推奨されません。  
  
 書き込み、メッセージ コンテキストからの読み取りと実行時のパフォーマンスに影響します。 一般に、アダプターでは、読み取り、書き込み、およびメッセージ コンテキスト プロパティの数が過剰に昇格を避ける必要があります。 プロパティの昇格は、実行時に昇格させたプロパティごとに発生するサブスクリプションの評価のため、追加のパフォーマンスのドレインを作成します。 ただし、アダプターは膨大な数のパフォーマンスに著しく影響するプロパティを昇格させる必要があります。 まだを昇格させるには、必要なプロパティのみを昇格させることをお勧めします。  
  
## <a name="throttle-send-and-receive"></a>スロットルの送受信  
 BizTalk エンジンの負荷が、構成されたしきい値を超えると、エンジンは、最適なパフォーマンスを確保するには、アダプターとオーケストレーションを調整します。 エンジンのワークロードが、アダプターの呼び出しに指定されたしきい値を超えたときに、受信側で**IBTTransportBatch.Done**負荷が十分に減少するまでブロックされます。 これにより、エンジンが使用可能な場合にのみ、エンジンに新しい作業を送信するアダプターです。 送信側では、エンジンがアダプター、送信メッセージの送信を制限するときに、エンジン配信しません、負荷が減少するまでに転送する新しいメッセージ。  
  
 これらの理由から、たとえば、必要な場合を除き、制限を考慮する、バックエンド システムへの接続の数を制限、アダプターは必要ありません。 これらの種類のシナリオのエンジンでも、アダプター フレームワークのサポートを提供します。  
  
 アダプターのソース コードを制御するかどうかに応じていくつかの方法でカスタムの送信アダプターから送信されたメッセージの数を調整を処理することができます。  
  
### <a name="send-side-throttling-improves-performance"></a>送信側の制限によるパフォーマンスを向上します。  
 アダプターのソース コードを制御する場合は、いつでも送信するキューに配置するメッセージの最大数をヒューリスティックによって決定します。 メッセージング エンジンを呼び出すと、`TransmitMessage`メソッドを呼び出し、新しいメッセージを送信アダプターか、以前に決定した最大値よりも大きい場合は、キュー内のメッセージの数を表示するか、またはスレッドをブロックする選択できます。 メッセージの最大数が超過した場合は使用できます、`Resubmit`メッセージング エンジンにメッセージを再送信する方法。 アダプターが同期の場合、メッセージが既にブロックされることに注意してください。  
  
 変更することによってキューに置かれたメッセージの数を変更するには、アダプターのソース コードを制御しない場合、 **Highwatermark** BizTalk 管理データベースの Adm_serviceclass テーブル内の値。 最大値、 **Highwatermark**プロパティは 200 です。 値を変更することも、**低レベルのウォーターマーク**プロパティ値を小さくします。  
  
 注意の値、 **Highwatermark**メッセージング エンジンがアダプターに指定されたメッセージの数のアカウントを非同期アダプターのプロパティ。 メッセージング エンジンからアダプターに渡します、`TransmitMessage`メソッドでは、これらのメッセージを送信をまだ未処理になる可能性 — たとえば、アダプターが対応する呼び出しを行っていない場合、 `DeleteMessage`、 `Resubmit`、 `MoveToNextTransport`、または[Microsoft.BizTalk.TransportProxy.Interop.BatchOperationType.MoveToSuspendQ](http://msdn.microsoft.com/library/microsoft.biztalk.transportproxy.interop.batchoperationtype.aspx)メソッド。 同期アダプターの場合、 **Highwatermark**のみを使用してアダプターに渡すがメッセージング エンジンは、メッセージの数のアカウントのプロパティ、 **TransmitMessage**メソッドのため、この呼び出し呼び出し元のメッセージング エンジン スレッドをブロックして同期的に処理します。  
  
 本質的にプロトコルの送信アダプターを作成する場合は、(HTTP、FTP、双方向の SOAP など) 低速な次を検討してください。  
  
- このようなアダプター BizTalk メッセージング エンジンからは、送信されるメッセージを送信可能なよりも速く受信可能性があります。 このような相違では、さまざまなレベルで問題が発生します。 送信中のメッセージはメモリに保持され、全体のシステム パフォーマンスの低下、仮想メモリを占有します。  
  
- アダプターは、プロトコル固有のリソースをかかる場合があります。 など、サーバーでは、リモート サーバーを中断させる可能性がへの多数の同時接続を開く、可能性があります。  
  
- 他のアダプターはアダプターの影響を与える可能性があります。 たとえば特定のアダプターのキューにメッセージが多すぎる、メッセージング エンジンはこのプロセスでは他の送信アダプターに対する要求の発行を停止します。  
  
  解決の方法では、低速で高速のアダプターを別の BizTalk ホストに配置して、"High Watermark"および"Low Watermark"の設定を使用してメッセージの数を制御します。  
  
### <a name="receive-side-throttling-improves-performance"></a>受信側の制限によるパフォーマンスを向上します。  
 これで、受信アダプターがメッセージをシステムの残りの部分がメッセージを処理できる速度よりも高速も多数あります。 このような状況が発生したときに、メッセージ ボックス データベースでバックログになります。 この場合、システム全体のパフォーマンスが大幅に低下します。  
  
 この場合は、アダプターで、受信アダプターの速度を下げる、次の手法のいずれかを使用できます。  
  
- メッセージング エンジン スレッドのプール サイズを減らします。 メッセージング エンジンを使用して、メッセージ ボックスにメッセージを公開するスレッドの数を制御することができます。 スレッドの数を減らすことでは、受信アダプターがメッセージ ボックスにメッセージを受信する速度を低下します。 のみ、この設定は、アダプターの受信ハンドラーに対応するホストを実行する必要があります。 設定しないでくださいこの、アダプターの送信ハンドラーに対応するホストの送信アダプターも速度が低下する場合を除き、します。  
  
- アダプターのバッチ サイズを削減します。 ほとんどの高速のアダプターの受信メッセージをバッチでメッセージ ボックス データベースに公開します。 これらのバッチのサイズは、受信場所のプロパティ ページで、通常は構成できます。 バッチ サイズを小さくして、システムに送信されるメッセージの全体的なスループットを減らすことができます。  
  
- その他のアダプターに固有の設定を変更します。 2 つの手順を完了すると、スループットをさらに軽減するには、その他のアダプター パラメーターを調整することもかまいません。 一部のアダプターでは、スループットを減らすために使用できる内部のパラメーターを公開します。 たとえば、設定を「順番に配信します」は、MQSeries アダプター 順次配送は、アダプターはメッセージのバッチの公開を完了するまで待機し、発行、次のバッチを指定します。 この設定を有効にすると、基本的に、受信アダプターからすべての並列処理を削除します。 逆に、受信アダプターの受信速度を向上させるには、反対の方向でパラメーターをチューニングを使用できます。  
  
  アダプターは、トランスポート プロキシに必要な数だけバッチを送信できます。 ときに、システム大きな負荷がかかってへの呼び出し、**完了**のメソッド、 **IBTTransportBatch**インターフェイス メッセージがシステムに必要なリソースが解放されるまでブロックされます。  
  
## <a name="plan-for-asynchronous-receive-and-send"></a>計画の非同期受信し、送信  
 豊富なが非同期プログラミングのサポート、BizTalk Server メッセージング Api にします。 スケーラブルなアダプターを記述する場合は、非同期モデルより優れた同時実行制御を提供するために、最初から非同期モデルを使用して計画します。  
  
 アダプターが BizTalk メッセージング エンジンにメッセージのバッチを送信すると、受信側で (を呼び出して**ibttransportbatch::done**)、メッセージング エンジンは、その内部スレッド プールを使用して作業をキューに配置しが直ちに返されます。 エンジンでは、完了する無料のソースからより多くのメッセージを読み取り、前のメッセージの処理を待たずに送信アダプターのまま、別のスレッドでメッセージを処理します。  
  
 送信側で、アダプターは、非同期または同期することができます。 ただし、プロトコルは、非同期操作をサポートする場合は、スケーラブルなアダプターを作成するこのサポートを使用する必要があります。 たとえば、ファイル サービスおよび HTTP は、アダプターは完全に非同期と非常にいくつかのブロック/同期操作を実行を送信します。  
  
 非同期操作では、メッセージング エンジンとアダプターの両方が並列で作業し、通常のメッセージ処理のため互いに待機しないし続けることを確認します。  
  
## <a name="use-batching-to-improve-performance"></a>パフォーマンスを向上させるためにバッチ処理の使用  
 スケーラブルなアダプターを作成するための最適な開始点は、バッチ処理します。 これは、送信側と受信側の両方のアダプターの場合は true。 すべてのバッチは、アダプターが非トランザクションである場合でも、BizTalk Server 内のデータベース トランザクションを通過します。 各トランザクションに関連付けられている一定の遅延があるため、1 つのバッチには、複数の操作を組み合わせることによってトランザクションの数を最小限にしようとする必要があります。  
  
## <a name="do-not-starve-the-net-thread-pool"></a>.NET スレッド プールの枯渇  
 アダプターは .NET ランタイム コードを記述する練習を BizTalk の書き込み.NET ランタイムを作成するコードが可変の非同期プログラミングの課題です。  
  
 .NET では、すべての非同期プログラミングのリスクは、.NET スレッド プールを枯渇させて、回避するために、BizTalk アダプターのプログラマにとって特に重要です。  
  
 .NET スレッド プールは、制限されていますが、広く共有リソースです。 .NET スレッド プールのスレッドのいずれかを使用して保持し、時間の長いから実行されている場合は、他の作業項目をブロックするコードを記述は簡単です。  
  
 使用するたびに**BeginInvoke**またはタイマーを使用して、.NET スレッド プールのスレッドを使用しています。 複数の処理を行うがある場合 (たとえば BizTalk Server にメッセージを MQSeries からをコピーする)、する必要があります実行 1 つの作業項目 (BizTalk Server にメッセージの 1 つのバッチ) し requeue スレッド プールで作業をすることがある場合します。 占有しないように、`while`スレッドでループします。  
  
 具体的に言うことを意味`while`ループを繰り返し呼び出すの**BeginInvoke**します。 この単純な変更は、応答性と実装全体のスケール アウト機能が大幅に向上します。  
  
## <a name="choose-the-right-measurement-when-limiting-batch-size"></a>バッチ サイズを制限する場合に適した単位を選択します。  
 BizTalk Server にメッセージをバッチを送信する場合は、メッセージ数のみに基づいてバッチ サイズは制限されません。 メッセージ数のみに基づくバッチをアダプターが構成されている場合の動作を考慮してください。2 つのバッチ サイズは、アダプターの 4 つのメッセージを取得する場合、それぞれ 4 KB、8 KB 1 MB 5 MB のサイズられる最初のバッチ サイズの 12 KB になり、2 つ目のバッチになります 6 MB のサイズを変更します。  
  
 BizTalk メッセージング エンジンが単一のバッチ内のすべてのメッセージを順番に処理するため、この例では、2 番目のバッチは最初のバッチに比べて大幅に低下処理されます。 スループットを効果的に削減これです。 この問題を処理する優れた方法では、メッセージ数とバッチ (バッチ サイズ (バイト単位) は、) の合計バイト数の両方に基づくバッチです。 合計バイト数のマジック ナンバーがありません。 ただし、通常の処理のシナリオでバッチ サイズが 1 MB を超える場合が始まりますが低い同時実行性とスループット。  
  
 一般に、アダプターはメッセージに依存しないと、運用環境でメッセージのサイズがわからない。 受信メッセージのサイズが大きく異なる可能性があります。 このため、常にバッチを構築するのにメッセージの数と合計バイト数を使用します。
---
title: "BizTalk Server での EDI 処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdc60423-24b6-4920-a870-520f575085ed
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b68781707211922d7d29958f896608c87358c7c0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="edi-processing-in-biztalk-server"></a>BizTalk Server での EDI の処理
このトピックでは、EDI メッセージの受信側と送信側の処理、および EDI メッセージングの実現における取引先アグリーメントの役割について説明します。  
  
## <a name="trading-partner-agreements-for-edi-processing"></a>EDI 処理の取引先アグリーメント  
 取引先アグリーメントは、BizTalk Server における EDI のサポートで重要な役割を再生します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における EDI 処理に関連したほとんどの構成機能および管理機能は、ビジネス プロファイル間の取引先アグリーメントを構成することによって実行されます。 アグリーメントには、両方の取引先の特定のビジネス プロファイルから、共通する双方向のメッセージ処理プロパティがまとめられます。 アグリーメントは、各ビジネス プロファイルに対して定義されたプロトコル設定に基づいて作成されます。 2 つのビジネス プロファイル間に取引先アグリーメントを実装するには、メッセージを交換する各ビジネス プロファイルのプロパティを定義します。 各ビジネス プロファイルのプロパティはインターチェンジ受信者およびインターチェンジ送信者として設定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信メッセージの処理または送信メッセージの生成を行うには、関係するアグリーメントと、メッセージに適用するスキーマを認識する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がアグリーメントを特定できない場合は、フォールバック取引先アグリーメントの TPM インターフェイスで定義されているプロパティを使用します。  
  
 TPM には EDIFACT プロパティ用および X12 プロパティ用の 2 つの主要なエンコード プロトコル設定のセットがあります。 これら 2 つのプロパティ セットはよく似ています。 プロトコル設定の詳細については、次を参照してください。[プロトコル設定](../core/protocol-settings.md)です。 契約の詳細については、次を参照してください。[取引先アグリーメント](../core/trading-partner-agreement.md)です。 プロトコル設定と取引先アグリーメントは、取引先管理 (TPM) ユーザー インターフェイスで設定します。 TPM の画面は、**パーティ**のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、開発者でなくても EDI 処理を構成できます。  
  
 詳細については、どのように取引のパートナー アグリーメント EDI 処理に役立つ、次を参照してください。 [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)です。  
  
## <a name="edi-receive-side-processing"></a>受信側の EDI 処理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDI メッセージを受信すると、EDI 受信パイプラインでメッセージを処理します。 受信パイプラインは、以下の基本的な処理を実行します。  
  
-   取引先アグリーメントの参照およびスキーマの決定を行います。  
  
    > [!NOTE]
    >  以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティの定義にアグリーメントの定義も含まれていました。 そのため、受信パイプラインがパーティのプロパティを検索する場合は、パーティの定義内でアグリーメント定義を内部的に検索してから、必要に応じてメッセージを処理します。 BizTalk Server で、パーティ (取引先) は、取引先アグリーメントと異なるため、受信パイプラインは検索、取引先アグリーメント具体的にはします。  
  
    > [!NOTE]
    >  メッセージが解決されるすべてのアグリーメントが無効になっている場合、メッセージは中断されます。 また、イベント ログに警告が記録されます。  
  
-   1 つの EDI メッセージに複数のインターチェンジが含まれている場合、インターチェンジを分割し、各インターチェンジを別々に処理します (この機能が有効な場合)。 詳細については、次を参照してください。 [、の複数インターチェンジの受信、単一メッセージ内の有効化](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md)です。  
  
-   各 EDI インターチェンジを解析し、X12 または EDIFACT でエンコードされたデータを XML ドキュメントに変換します。  
  
-   EDI 標準、パートナー アグリーメント、およびメッセージ スキーマに従ってエンベロープとそのメッセージを検証します。  
  
-   インターチェンジがバッチ処理されている場合は、バッチ処理されているインターチェンジを分割して、トランザクション セットごとに XML ファイルを作成し、バッチ処理に必要なプロパティを昇格させるか、インターチェンジを保持します。  
  
-   受信確認を生成します。  
  
-   EDI エンベロープをコンテキスト プロパティに変換し、EDI 処理のための他のプロパティを昇格させます。  
  
-   バッチ処理を制御するプロパティを昇格させます。 これには、バッチ解除されたトランザクション セットを複数のパーティに送信することが含まれることもあります。  
  
 受信側の EDI 処理を使用する場合は、次の点を考慮する必要があります。  
  
-   受信場所では、あらゆる種類のトランスポートを使用できます。  
  
-   受信側の EDI 処理の詳細については、次を参照してください。[どのように BizTalk Server 受信 EDI メッセージ](../core/how-biztalk-server-receives-edi-messages.md)です。  
  
-   受信パイプラインで EDI 逆アセンブラーによって実行される特定の処理の詳細については、次を参照してください。 [「EDI 逆アセンブラーの動作](../core/how-the-edi-disassembler-works.md)です。  
  
## <a name="edi-batch-processing"></a>EDI バッチ処理  
 受信メッセージがバッチである場合、EDI 受信パイプラインは構成に応じて、バッチ処理されたインターチェンジをその構成トランザクション セットに分割するか、バッチ処理されたインターチェンジを保持します。 EDIReceive パイプラインは BatchMarker パイプライン コンポーネントを使用して、バッチ処理するインターチェンジをすべてバッチ処理オーケストレーションまたはルーティング オーケストレーションにルーティングします。  
  
 受信側の処理の後、バッチ処理の対象のトランザクション セットはバッチ処理オーケストレーションによって処理されます。 バッチ処理オーケストレーションは、フィルター条件、アクティベーションの範囲、およびリリース条件に基づいてバッチを作成します。  
  
 バッチ処理されていない EDI トランザクション セットをバッチに送信する必要がある場合は、ルーティング オーケストレーションがトランザクション セットを処理します。 一致するバッチのそれぞれに対してトランザクション セットのコピーが作成されます。  
  
 バッチ処理で実行される特定の処理の詳細については、次を参照してください。[着信バッチの処理](../core/processing-incoming-batches.md)または[送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)です。  
  
## <a name="edi-send-side-processing"></a>送信側の EDI 処理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送信 EDI メッセージを生成して送信すると、EDI 送信パイプラインでメッセージが処理されます。 送信パイプラインは、以下の処理を実行します。  
  
-   取引先アグリーメントの参照およびスキーマの決定を行います。  
  
    > [!NOTE]
    >  以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティの定義にアグリーメントの定義も含まれていました。 そのため、送信パイプラインがパーティのプロパティを検索する場合は、パーティの定義内でアグリーメント定義を内部的に検索してから、必要に応じてメッセージを処理します。 BizTalk Server で、パーティ (取引先) は、取引先アグリーメントと異なるため、送信パイプラインは検索、取引先アグリーメント具体的にはします。  
  
    > [!NOTE]
    >  メッセージが解決されるすべてのアグリーメントが無効になっている場合、メッセージは中断されます。  また、イベント ログに警告が記録されます。  
  
-   EDI メッセージをシリアル化し、X12 または EDIFACT でエンコードされたデータに XML ドキュメントを変換します。  
  
-   X12 の区切り文字としても使用される文字がメッセージ データに含まれる場合は、ペイロードの文字を別の文字に置き換えるように送信パイプラインを構成できます。  
  
-   EDI メッセージがバッチ処理されたインターチェンジの場合、送信パイプラインは、バッチ処理オーケストレーションでバッチが構築された後、BizTalk MessageBox からインターチェンジを取得します。  
  
-   送信メッセージを検証します。  
  
-   実行時に指定されたパーティのプロパティまたは EDI エンベロープのプロパティに従って、EDI エンベロープを作成します。  
  
-   受信した受信確認を処理します。  
  
 送信側の EDI 処理を使用する場合は、次の点を考慮する必要があります。  
  
-   送信ポートでは、あらゆる種類のトランスポートを使用できます。  
  
-   送信側の EDI 処理の詳細については、次を参照してください。[どのように BizTalk Server 送信 EDI メッセージ](../core/how-biztalk-server-sends-edi-messages.md)です。  
  
-   送信パイプラインで実行される特定の処理の詳細については、次を参照してください。 [「EDI アセンブラーの動作](../core/how-the-edi-assembler-works.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server における EDI のサポート](../core/edi-support-in-biztalk-server1.md)   
 [EDI のサポートに関する問題](../core/edi-support-issues.md)   
 [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)   
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)   
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)   
 [BizTalk Server EDI ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
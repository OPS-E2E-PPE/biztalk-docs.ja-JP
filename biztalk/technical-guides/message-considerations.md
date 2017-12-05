---
title: "メッセージの考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ca466fa-426c-46f6-a400-747ff51ff8f4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a277149a47fa60dda4df9291ec437ac67c518fdd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="message-considerations"></a>メッセージの考慮事項
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信、受信、変換、およびメッセージの処理の広範な機能セットを提供します。 これらの機能が含まれます。  
  
-   HTTP、SMTP、FTP または FTPS、WCF などの複数の業界標準トランスポートを使用してメッセージを送受信する機能。 使用してメッセージを送受信するためのトランスポート レベルのサポートを実現[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。 統合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまな「基幹業務」でメッセージを処理 (LOB) アプリケーションは利用可能な次のいずれかを使用して実現[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アクセラレータまたは BizTalk Accelerator 用 HIPAA、BizTalk Accelerator 用 SWIFT などのアダプターまたは、BizTalk の SAP アダプターを選択します。 これらのアクセラレータとアダプターの簡単な統合をさらに対応する業界標準に準拠して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定業界標準に準拠しているシステムとします。  
  
-   プレーン テキスト、XML、バイナリなどの複数のメッセージ形式と他のユーザーを処理する権限です。 この機能は、の統合を提供するために重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多様な取引先とします。  
  
-   メッセージの変換またはドキュメントのマッピングをサポートします。 マッピングには、さまざまなスキーマ間のデータの変換が対応しています。 たとえば、マッピングを使用して、顧客に送信する出荷通知を受信受信した顧客の注文書の内容を変換する可能性があります。  
  
-   BizTalk Server オーケストレーションは、時間、組織、アプリケーション、およびユーザーにまたがるビジネス プロセスを作成するための機能を提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](従来の「原子」MSDTC 型、長時間実行の両方)、トランザクションのサポートを含むビジネス プロセスを開発するオーケストレーション デザイナーのグラフィカル インターフェイスを提供する例外処理、デバッグ、追跡、および呼び出し元の機能拡張外部コードです。  
  
    > [!NOTE]  
    >  参照してください[オーケストレーションのパフォーマンスの最適化](../technical-guides/optimizing-orchestration-performance.md)でオーケストレーションを使用するときに従うベスト プラクティスに関するガイダンスについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 トピックを参照して[オーケストレーション デザイナーを使用してオーケストレーションを作成する](http://go.microsoft.com/fwlink/?LinkId=158997)(http://go.microsoft.com/fwlink/?LinkId=158997) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション デザイナーの使用の詳細についてはドキュメントです。  
  
 このトピックの残りの部分では、BizTalk Server 環境で処理されるメッセージのサイズ、複雑さ、および配布のプロファイルに関連するパフォーマンスの考慮事項について説明します。  
  
## <a name="message-size-considerations"></a>メッセージのサイズに関する考慮事項  
 BizTalk Server には、メッセージのサイズに制限はありません、ときに実際の制限値との依存関係する必要がありますサイズの大きいメッセージより多くの処理リソースを必要とするために、メッセージのサイズを最小化します。 同様のメッセージのサイズが増えると、全体的なスループット (1 秒あたりに処理されるメッセージ) が減少します。 ときにシナリオを設計し、容量の計画は、メッセージの平均サイズ、メッセージの種類、および BizTalk Server で処理するメッセージの数を検討します。 不必要に長く属性とタグ名を使用しないでください。可能であれば、50 文字の長さを保持します。 たとえば、1 バイトしかのメッセージ サイズを 200 文字タグ名を使わないでください。  
  
 メッセージをフラグメントに分割が受信したメッセージのメモリ内サイズは、サイズの大きいメッセージのフラグメント サイズ (BizTalk Server 管理コンソールで BizTalk グループのグループのプロパティ ページで構成可能) の指定されたバイト数を超えている場合指定したサイズ。 さらに、フラグメントが書き込まれます Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストでメッセージ ボックスに次のようにします。  
  
1.  受信メッセージは、既存の MSDTC トランザクションのコンテキストで公開されているが、このトランザクションが、BizTalk メッセージ ボックス データベースに、メッセージのフラグメントを書き込むときに使用されます。 たとえば、受信メッセージは、トランザクションを要求するように構成されたトランザクション アダプターによって公開されているが場合、既存のトランザクションが使用されます、メッセージのフラグメントをメッセージ ボックス データベースに書き込むとき。  
  
2.  受信メッセージが既存の MSDTC トランザクションのコンテキストで公開されていない場合に、メッセージのフラグメントをメッセージ ボックス データベースに書き込めません、新しい MSDTC トランザクションが作成されます。 このシナリオでは、次の考慮事項が適用されます。  
  
    -   値を大きく**サイズの大きいメッセージのフラグメント サイズ**をサイズの大きいメッセージが断片化しているし、関連付けられた MSDTC トランザクションの作成の発生頻度を減らす頻度を減らす方法。 MSDTC トランザクションを使いすぎるとパフォーマンスの観点で無駄が多いため、この操作を実行する必要があります。 この値を大きくすると使用できるメモリの量も増える可能性があるので注意してください。  
  
    -   最大許容 MSDTC トランザクションのタイムアウト値は、メッセージ ボックス データベースにメッセージを書き込む 60 分より長くかかる、トランザクションがタイムアウト エラーが発生すると、メッセージの書き込みを試みると失敗がロールバックされます。 **サイズの大きいメッセージのフラグメント サイズ**値にする必要がありますを非常に大きなメッセージを処理するときに、この問題を避けるために増加します。 使用できるメモリの量に応じて、この値を最大値 1000000 バイトに設定する必要があります。  
  
    -   メッセージの各フラグメントは、メッセージ ボックス データベースに対して 1 つ以上の SQL Server データベース ロックを作成します。 ロックの数が数十万を超える場合、SQL Server が"ロック"の範囲外のエラーを生成することができます。 この問題が発生した場合の値を大きく**サイズの大きいメッセージのフラグメント サイズ**(これは、メッセージ ボックス データベースに対して行われた SQL Server データベース ロックの数は減少) フラグメントの数を減らしてまたはハウジングを検討してください、64 ビット バージョンの SQL Server でメッセージ ボックス データベースです。 使用可能なロックの数よりも SQL Server の 32 ビット バージョンの SQL Server 上の 64 ビット バージョンで大幅に高くなります。 次の数式は、32 ビット バージョンの SQL Server で、メッセージ ボックス データベースが格納されているときに、インターチェンジごとのメッセージの最大数を推定を使用できます。  
  
        ```  
        200,000 / (Number of CPUs * BatchSize * MessagingThreadPoolSize)  
        ```  
  
 BizTalk Server がサイズの大きいメッセージを処理するためのガイドラインなど、サイズの大きいメッセージを処理する方法の詳細については、次を参照してください。[どのように BizTalk Server プロセス サイズの大きいメッセージ](http://go.microsoft.com/fwlink/?LinkID=154680)(http://go.microsoft.com/fwlink/?LinkID=154680)。  
  
## <a name="message-type-considerations"></a>メッセージ型に関する考慮事項  
 2 つの主な形式のいずれかで BizTalk Server にメッセージを受信します。 XML ファイルまたはフラット ファイル。 メッセージの種類は、XML とフラット ファイル メッセージのさまざまなリソース要件のためメッセージのディストリビューション プロファイルに常に組み込む必要があります。  
  
-   **XML ファイル**BizTalk Server でパススルー ルーティング以外のメッセージ処理を実行するためには、メッセージが XML ファイルの形式である必要があります。  
  
-   **フラット ファイル**フラット ファイルは BizTalk Server でパススルー ルーティング以外の処理を行う前に、XML 形式に解析する必要があります。 XML ファイルでフラット ファイルを解析すると、ファイルのサイズが非常に大きくなる可能性があります。 フラット ファイルには、データに関する説明情報を持つ XML タグが含まれません。 一方、XML ファイルは、説明的な XML タグにすべてのデータを格納します。 一部のシナリオで解析サイズを増やしフラット ファイルのファイルの XML タグに 10 以上、に応じてどの程度わかりやすいデータが含まれているという因数によってです。  
  
-   **フラット ファイル ドキュメントの XML ドキュメントに単一の CDATA セクション ノードでラップ**全体にフラット ファイル ドキュメントをラップする BizTalk Server に読み込む必要がありますので、この種類のドキュメントはメモリの消費量は、多くの場合、XML とフラット ファイルの両方の組み合わせ処理する前にメモリ。  
  
## <a name="overload-considerations"></a>オーバー ロードに関する考慮事項  
 ほとんどの BizTalk Server アプリケーションでは、定数、特定のレートでメッセージは表示されません。 通常、メッセージの処理は、上下の対象です。 、たとえば、オンライン バンキング アプリケーション可能性があります処理、より大量のメッセージの最初に、朝でクリックし、1 日の終わりと、1 日の中にします。 BizTalk Server ソリューションをテストする必要がありますを処理できることを確認するこれらのオーバー ロードのシナリオです。 ソリューションを処理できる BizTalk Server、オーバー ロードのシナリオの度合いを判断するのには、BizTalk Server ソリューションの最大の維持可能なスループット (MST) を決定してください。 MST は、システムが実稼働環境で無制限に処理できるメッセージ トラフィックの最大負荷です。 MST の詳細については、次を参照してください。[継続的なパフォーマンスの計画](http://go.microsoft.com/fwlink/?LinkID=158065)(http://go.microsoft.com/fwlink/?LinkID=158065) および[維持可能なパフォーマンスは何ですか。](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
## <a name="schema-complexity"></a>スキーマの複雑さ  
 メッセージの解析中の (特にフラット ファイル解析) のスループットは、スキーマの複雑さによって異なります。 スキーマの複雑さが多いほど、全体的なパフォーマンスが低下します。 スキーマを設計する場合は、ノード名の長さを短くし、昇格させたプロパティをスキーマの最上部に移動します。 これにより、検索時間が短縮され、それによってパフォーマンスが向上します。  
  
## <a name="map-complexity"></a>マップの複雑さ  
 マップの複雑さ、によってマップ変換にリソースを消費することができます。 としてのマップの複雑さが増えると、全体的なパフォーマンスが低下します。 全体的なパフォーマンスを向上させるのには、リンクと、マップでは、特にの DB 検索 functoid などの外部リソースを呼び出す functoid で使用される functoid の数を最小限に抑えます。  
  
## <a name="flat-file-parsing-considerations"></a>フラット ファイル解析の考慮事項  
 フラット ファイル解析のパフォーマンスに最大の影響のある 2 つの要素は、ファイルのサイズとスキーマの複雑さです。 あいまいなスキーマは、多くの省略可能なフィールドを含むスキーマです。 も大きなファイルがスキーマのそれぞれの分岐を一致可能性があるため大きなファイルのサイズを使用している場合に、多くの省略可能なフィールドを持つスキーマでパフォーマンスが低下します。 スキーマの複雑さより小さいファイルをよりも大きなファイル上で以下の影響を及ぼします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)
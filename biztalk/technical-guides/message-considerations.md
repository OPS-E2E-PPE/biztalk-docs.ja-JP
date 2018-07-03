---
title: メッセージの考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ca466fa-426c-46f6-a400-747ff51ff8f4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8a9bcf8b2910f12183db33aa27a74b550c72b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979683"
---
# <a name="message-considerations"></a>メッセージの考慮事項
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信、受信、変換、およびメッセージの処理には、広範な機能セットを提供します。 これらの機能のいくつか挙げます。  
  
- HTTP、SMTP、FTP または FTPS、および WCF などの複数の業界標準トランスポートを使用してメッセージを送受信する機能。 使用してメッセージを送受信するためのトランスポート レベルのサポートを実現[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。 統合の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまな「基幹業務」でメッセージの処理 (LOB) アプリケーションが使用可能な次のいずれかを使用して実現[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アクセラレータまたは BizTalk Accelerator 用 HIPAA、BizTalk Accelerator for SWIFT などのアダプターまたは、BizTalk の SAP アダプターを選択します。 これらのアダプターとアクセラレータは、さらに簡単に統合に対応する業界標準に準拠している[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定業界標準に準拠しているシステムとします。  
  
- プレーン テキスト、XML、バイナリなどの複数のメッセージ形式と他のユーザーを処理する権限です。 この機能は、の統合を提供するために重要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多様な取引にします。  
  
- メッセージの変換またはドキュメントのマッピングをサポートします。 マッピングには、さまざまなスキーマ間のデータの変換が対応しています。 たとえば、マッピングを使用して、顧客に送信する出荷通知の受信に受信した顧客の注文書の内容を変換する可能性があります。  
  
- BizTalk Server オーケストレーションは、時間、組織、アプリケーション、およびユーザーにまたがるビジネス プロセスを作成するための機能を提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (従来の「アトミック」MSDTC 型、長時間トランザクションの両方)、トランザクションのサポートを含むビジネス プロセスを開発するオーケストレーション デザイナーのグラフィカル インターフェイスを提供する例外処理、デバッグ、追跡、および呼び出し元の機能拡張外部コードです。  
  
  > [!NOTE]
  >  参照してください[オーケストレーションのパフォーマンスの最適化](../technical-guides/optimizing-orchestration-performance.md)でオーケストレーションを使用する場合に従うベスト プラクティスに関するガイダンスについては[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 トピックを参照して[オーケストレーション デザイナーを使用してオーケストレーションを作成](http://go.microsoft.com/fwlink/?LinkId=158997)(<http://go.microsoft.com/fwlink/?LinkId=158997>) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション デザイナーの使用の詳細についてはドキュメントです。  
  
  このトピックの残りの部分では、BizTalk Server 環境で処理されるメッセージのサイズ、複雑さ、および配布プロファイルに関連するパフォーマンスの考慮事項について説明します。  
  
## <a name="message-size-considerations"></a>メッセージのサイズに関する考慮事項  
 BizTalk Server には、メッセージのサイズに制限はありません、中に実質的な制限と依存関係を行う必要はサイズの大きいメッセージより処理リソースを必要とするために、メッセージのサイズを最小限に抑えます。 同様のメッセージのサイズが増えると、全体的なスループット (1 秒あたりに処理されるメッセージ) が減少します。 ときにシナリオを設計し、容量計画は、メッセージの平均サイズ、メッセージの種類、および BizTalk Server で処理するメッセージの数を検討します。 不必要に長い属性とタグの名前を使用しないでください。可能であれば、50 文字の長さを維持します。 たとえば、メッセージ サイズは 1 バイトしかを 200 文字のタグ名は使用しないでください。  
  
 受信したメッセージのメモリ内サイズを超えるサイズの大きいメッセージのフラグメント サイズ (BizTalk Server 管理コンソールで BizTalk グループのグループのプロパティ ページで構成可能) 指定されたバイト数と、メッセージがフラグメントに分割されます。指定したサイズ。 さらに、フラグメントが書き込まれます Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストでメッセージ ボックスに次のようにします。  
  
1. 受信メッセージは、既存の MSDTC トランザクションのコンテキストで公開されているが、このトランザクションは、メッセージのフラグメントを BizTalk メッセージ ボックス データベースに書き込むときに使用されます。 たとえば、受信メッセージは、トランザクションを要求するように構成されたトランザクション アダプターによって公開されているが場合、既存のトランザクションは使用、メッセージのフラグメントをメッセージ ボックス データベースに書き込むときに。  
  
2. 受信メッセージが既存の MSDTC トランザクションのコンテキストで公開されていない場合、メッセージのフラグメントをメッセージ ボックス データベースに書き込む新しい MSDTC トランザクションが作成されます。 このシナリオでは、次の考慮事項が適用されます。  
  
   -   値を大きく**サイズの大きいメッセージのフラグメント サイズ**がサイズの大きいメッセージが断片化しているし、関連付けられた MSDTC トランザクションの作成の頻度を減らすの頻度を減らします。 MSDTC トランザクションを使いすぎるとパフォーマンスの観点で無駄が多いため、この操作を実行する必要があります。 この値を大きくすると使用できるメモリの量も増える可能性があるので注意してください。  
  
   -   最大許容される MSDTC トランザクションのタイムアウト値をメッセージ ボックスにメッセージを書き込む 60 分より長くかかるトランザクション タイムアウトし、エラーが発生すると、メッセージを書き込む試行が失敗し、ロールバックされます。 **サイズの大きいメッセージのフラグメント サイズ**値は非常に大きなメッセージを処理するときに、この問題を回避するために大ききます。 使用できるメモリの量に応じて、この値を最大値 1000000 バイトに設定する必要があります。  
  
   -   メッセージの各フラグメントは、メッセージ ボックス データベースに対して 1 つ以上の SQL Server データベース ロックを作成します。 ロックの数が数十万を超える場合 SQL Server が"ロック"の範囲外のエラーを生成することができます。 この問題が発生した場合の値を大きく**サイズの大きいメッセージのフラグメント サイズ**(これは、メッセージ ボックス データベースに対して行われた SQL Server データベース ロックの数を減らす) フラグメントの数の削減やハウジングを検討してください、64 ビット バージョンの SQL Server でメッセージ ボックス データベースです。 使用可能なロックの数よりも SQL Server の 32 ビット バージョンの SQL Server での 64 ビット バージョンでは大幅に高くなっています。 次の数式は、32 ビット バージョンの SQL Server にメッセージ ボックス データベースが格納されているときに、インターチェンジごとのメッセージの最大数を推定を使用できます。  
  
       ```  
       200,000 / (Number of CPUs * BatchSize * MessagingThreadPoolSize)  
       ```  
  
   BizTalk Server がサイズの大きいメッセージを処理するためのガイドラインなど、サイズの大きいメッセージを処理する方法の詳細については、次を参照してください。[どのように BizTalk Server プロセス サイズの大きいメッセージ](http://go.microsoft.com/fwlink/?LinkID=154680)(http://go.microsoft.com/fwlink/?LinkID=154680)します。  
  
## <a name="message-type-considerations"></a>メッセージの種類に関する考慮事項  
 2 つの主な形式のいずれかで BizTalk Server にメッセージを受信する: XML ファイルまたはフラット ファイル。 メッセージの種類は、XML とフラット ファイル メッセージのさまざまなリソース要件のためメッセージの配布プロファイルに常にファクタリングする必要があります。  
  
-   **XML ファイル**BizTalk Server でパススルー ルーティング以外のメッセージ処理を実行するためには、メッセージは、XML ファイル形式である必要があります。  
  
-   **フラット ファイル**フラット ファイルは、BizTalk Server でパススルー ルーティング以外の処理を行う前に、XML 形式に解析する必要があります。 XML ファイルでフラット ファイルを解析すると、ファイルのサイズが非常に大きくなる可能性があります。 フラット ファイルには、データに関する説明情報を持つ XML タグが含まれません。 一方、XML ファイルは、説明的な XML タグにすべてのデータを格納します。 一部のシナリオで解析サイズを増やし、フラット ファイルのファイルの XML タグに 10 個以上、に応じてどの程度わかりやすいデータが含まれているの倍数で。  
  
-   **フラット ファイル ドキュメントの XML ドキュメントの単一の CDATA セクション ノードでラップ**全体がフラット ファイル ドキュメントをラップするので、BizTalk Server に読み込む必要がありますこの種類のドキュメントが XML とフラット ファイルの両方の組み合わせですし、大量のメモリを多くの場合は、処理する前にメモリ。  
  
## <a name="overload-considerations"></a>オーバー ロードに関する考慮事項  
 ほとんどの BizTalk Server アプリケーションは、特定の定数のレートでメッセージを受信しません。 通常、メッセージの処理は、山と谷の対象です。 、たとえば、オンライン銀行取引アプリケーション可能性があります処理、より大量のメッセージの最初と 1 日の最後に、1 日の中にし、午前中は、します。 BizTalk Server ソリューションをテストする必要がありますを処理できることを確認するこれらのオーバー ロードのシナリオ。 ソリューションが処理できる BizTalk Server がどの程度シナリオをオーバー ロードを確認するのには、BizTalk Server ソリューションの最大の持続スループット (MST) を決定してください。 MST は、システムが実稼働環境で無制限に処理できるメッセージ トラフィックの最大負荷です。 MST の詳細については、次を参照してください[パフォーマンス維持の計画](http://go.microsoft.com/fwlink/?LinkID=158065)(<http://go.microsoft.com/fwlink/?LinkID=158065>) と[維持可能なパフォーマンスとは何ですか?。](http://go.microsoft.com/fwlink/?LinkID=132304) (<http://go.microsoft.com/fwlink/?LinkID=132304>) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
## <a name="schema-complexity"></a>スキーマの複雑性  
 メッセージの解析 (特に、フラット ファイル解析) のスループットは、スキーマの複雑さの影響を受けます。 スキーマの複雑さの増大に合わせて、全体的なパフォーマンスが低下します。 スキーマを設計するときは、ノード名の長さを短くし、昇格させたプロパティをスキーマの先頭に移動します。 これにより、検索時間が短くなり、それによってパフォーマンスが向上します。  
  
## <a name="map-complexity"></a>マップの複雑さ  
 マップの複雑さ、によってマップ変換にリソースを消費することができます。 同様のマップの複雑さが増えると、全体的なパフォーマンスが低下します。 全体的なパフォーマンスを向上させるのには、リンクおよび functoid の DB 検索 functoid などの外部リソースを呼び出す functoid 特に、マップで使用される数を最小限に抑えます。  
  
## <a name="flat-file-parsing-considerations"></a>フラット ファイル解析の考慮事項  
 フラット ファイル解析のパフォーマンスに最大の影響がある 2 つの要素は、ファイルのサイズとスキーマの複雑さです。 あいまいなスキーマは、多くの省略可能なフィールドを含むスキーマです。 大きなファイルのスキーマの異なるブランチが一致するためより大きなファイル サイズを使用している場合に、多くの省略可能なフィールドを持つスキーマでパフォーマンスが低下します。 スキーマの複雑性より大きなファイルをより小さなファイルに以下の影響を及ぼします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)
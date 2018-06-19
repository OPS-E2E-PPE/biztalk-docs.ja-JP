---
title: BizTalk adapter 用 Siebel eBusiness Applications の制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limitations of, Siebel adapter
- Siebel adapter, limitations of
ms.assetid: fda63dd6-bad5-4f6d-8cc1-5855efb6f063
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9018c79e910c2bfac05f07466cbeeb79ea045ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222650"
---
# <a name="limitations-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk adapter 用 Siebel eBusiness Applications の制限事項
次はの既知の制限、 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]:  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Microsoft BizTalk Adapter 用 Siebel eBusiness Applications、以前のリリースのアダプターの互換性がありません。 アダプターの現在のリリースは、アダプターの以前のバージョンを使用して生成されたスキーマを持つメッセージの送受信をサポートしていません。  
  
    > [!NOTE]
    >  以前のバージョン、新しい Siebel アダプターの BizTalk プロジェクトを変更する WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 詳細については、次を参照してください。[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)です。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ワークフロー オブジェクトをサポートしていません。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]をクライアントが Siebel システムに時刻値を渡す形式では検証されません。 アダプターのクライアントは、日付と時刻のフィールドに指定された値は、Siebel システムが期待する形式に準拠していることを確認してください。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]スキーマ検証は実行されません。 たとえば、長さ 30 のフィールドかかります値 100、長さと Siebel システムで許可されている場合。 ためにを招く可能性の特定のシナリオでデータ損失に、クライアントは、ビジネス オブジェクトを挿入するデータをできない可能性があります必ずしも実際には、データベースに書き込まれるデータ。 アダプター クライアントでは、アダプターによって公開されるスキーマに対して入力を検証する必要があります明示的にします。 ただし、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は検証を必要なすべてのフィールド (ビジネス コンポーネント) または (ビジネス サービス) 用の引数を指定します。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel の標準の形式で指定する時間の値が必要です: は HH:MM:SS です。 時刻の値で指定されたいずれかの他の形式には、エラーが発生し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]スロー、`TargetSystemException`です。  
  
-   特定のシナリオでは、Siebel アプリケーションは、可能性がありますか、エラー メッセージをスローしません可能性があります。 たとえば、式を使用して、検索操作可能性があります例外をスローまたはゼロ accords を返します。 同様に、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]スローする可能性があります、`TargetSystemException`または出力として空の XML を取得します。  
  
-   WCF サービス モデルを使用して、Siebel システムからデータを取得中に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 65536 以上のノードを持つ Xml を逆シリアル化ではありません。 出力 XML に 65536 のノード少ないがあることを確認してください。 この制限は、アプリケーションの app.config ファイルを変更することで回避できます。 手順については、次を参照してください。 [Siebel アダプターでの運用上の問題をトラブルシューティング](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)です。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]データベース層ではなく、ビジネス コンポーネントのレイヤーからのフィールドの最大長を取得します。 そのため、データベース列の最大長に準拠するが、ビジネス コンポーネントの対応するフィールドの最大長より大きい値を挿入しようとする場合、データベースに書き込まれた値可能性がありますが必要な値と異なる入力します。  
  
-   バッチ操作 (Insert、Update、および Delete) の実行中に、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]最初の操作結果エラーになった場合はエラーをスローします。 ただし、最初の操作が成功し、後続の操作のいずれかが失敗すると、アダプターはエラーはスローされませんが出力に成功した操作に対応するレコードの Id ではなくを返します。 アダプターのクライアントのすべての操作を正常に実行されているかどうかを確認する必要があります明示的にします。  
  
-   基になる Siebel クライアント API によるタイムアウトの処理に関する問題のため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
-   Siebel の"A"のユーザーが操作のメタデータを生成するシナリオを検討してください。 "B","A"のユーザーよりも低い権限を持つ別のユーザーは、メタデータにアクセスできるようにします。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] "B"のユーザーは、メタデータへのアクセスを取得する必要があるかどうかを検証するには、どのチェックは実行されません。 ただし、特権がないためユーザー"B"できないことがあります、メタデータを使用して、Siebel システムに任意の操作を実行します。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]パラメーター値のいずれかの特殊文字が含まれている URI の接続の指定をサポートしていません。 特殊文字を含むパラメーター値ごとに、特殊文字をエンコード標準の URI で指定された、対応する値に置き換えていることを確認します。  
  
-   アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF カスタムの資格情報の送信ポートが正しくない要求メッセージは処理されません。 正しい資格情報を指定すると後、メッセージは、Siebel システムに送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。 このようなシナリオでは、ホスト インスタンスを再起動する必要があります。  
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)
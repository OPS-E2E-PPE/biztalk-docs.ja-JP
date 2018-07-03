---
title: BizTalk Adapter 用 Siebel eBusiness Applications の制限事項 |Microsoft Docs
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
ms.openlocfilehash: e47e558ccf0d9841c47911490c1cee319515fd90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019446"
---
# <a name="limitations-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk Adapter 用 Siebel eBusiness Applications の制限事項
次の制限事項を呼びます、 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]:  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は Microsoft BizTalk Adapter 用 Siebel eBusiness Applications、以前のリリースのアダプターの互換性がありません。 アダプターの現在のリリースは、アダプターの以前のバージョンを使用して生成されたスキーマを含むメッセージを送受信することをサポートしていません。  
  
  > [!NOTE]
  >  新たに使用する Siebel アダプターの以前のバージョンの BizTalk プロジェクトを変更する WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 詳細については、次を参照してください。[を移行する BizTalk プロジェクト作成を使用して前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)します。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ワークフロー オブジェクトをサポートしていません。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]をクライアントが Siebel システムに時刻値を渡す形式を検証しません。 アダプター クライアントは、日付と時刻のフィールドに指定された値は、Siebel システムが期待する形式に準拠していることを確認してください。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]スキーマ検証は実行されません。 など長さ 30 のフィールドは、Siebel システムで許可されている場合、長さが 100 の値をできます。 クライアントは、ビジネス オブジェクトを挿入するデータをできない可能性がありますとは限りませんが、実際にデータベースに書き込まれたデータために、特定のシナリオでのデータの損失を招くも可能性があります。 アダプター クライアントは、入力アダプターによって表示されるスキーマに対して明示的に検証する必要があります。 ただし、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は検証を必要なすべてのフィールド (用ビジネス コンポーネント) または (ビジネス サービス) 用の引数を指定します。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で時刻の値を標準の Siebel 形式で指定する必要があります: は HH:MM:SS です。 時刻の他の形式には、エラーが発生するいずれかで指定されている値と[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]スロー、 `TargetSystemException`。  
  
- 特定のシナリオでは、Siebel アプリケーションは、可能性がありますか、エラー メッセージをスローしない可能性があります。 たとえば、式を使用して、検索操作可能性があります例外をスローまたは accords 0 を返します。 したがって、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]をスローする可能性を`TargetSystemException`または出力として空の XML を取得します。  
  
- WCF サービス モデルを使用して Siebel システムからデータを取得中に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 65536 の複数のノードが存在する Xml を逆シリアル化ではありません。 XML 出力が 65536 のノード以下を確認します。 この制限を回避するには、アプリケーションの app.config ファイルを変更します。 手順については、次を参照してください。 [Siebel アダプターでの運用上の問題をトラブルシューティング](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)します。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]データベース層ではなく、ビジネス コンポーネント レイヤーからフィールドの最大長を取得します。 そのため、データベースの列の最大長に準拠するが、ビジネス コンポーネントの対応するフィールドの最大の長さより大きい値を挿入しようとする場合、データベースに書き込まれた値異なる可能性がありますと値入力します。  
  
- バッチ操作 (Insert、Update、および Delete) の実行中に、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]最初の操作結果エラーの場合は、エラーをスローします。 ただし、最初の操作が成功すると、後続の操作の失敗した場合は、アダプターは、エラーをスローしませんではなく、出力に成功した操作に対応するレコードの Id を返します。 アダプター クライアントは、すべての操作が成功したかどうかを明示的に確認する必要があります。  
  
- 基になる Siebel クライアント API によってタイムアウト処理に関する問題のため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
- Siebel の"A"のユーザーが操作のメタデータを生成するシナリオを検討してください。 "B"、"A"のユーザーよりも低い特権を持つ別のユーザーは、メタデータにアクセスできるようにします。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] "B"のユーザーは、メタデータへのアクセスを取得する必要があるかどうかを検証するには、どのチェックは実行されません。 ただし、ため、十分な特権ユーザー"B"できないことがあります、メタデータを使用して、Siebel システムに対して任意の操作を実行します。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続パラメーター値のいずれかの特殊文字を含む URI を指定することはできません。 特殊文字が含まれる各パラメーター値の特殊文字をエンコード標準の URI で指定したとおり、対応する値に置き換えていることを確認します。  
  
- アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、資格情報、Wcf-custom 送信ポートが正しくない要求メッセージは処理されません。 正しい資格情報を指定した後、Siebel システムにメッセージを送信し、応答を受信します。 ただし、応答メッセージでは、出力ポートを使用できません。 このようなシナリオでは、ホスト インスタンスを再起動する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Siebel eBusiness Applications について](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)
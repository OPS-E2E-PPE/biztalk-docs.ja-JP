---
title: ビジネス ルール エンジン (BRE) のパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c271b059-174d-4e8b-88b5-c3f408a97f1f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18fdd1e642d211a79f591f5029dcd37ac618011b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242635"
---
# <a name="optimizing-business-rule-engine-bre-performance"></a>ビジネス ルール エンジン (BRE) のパフォーマンスを最適化します。
BizTalk Server ソリューションでビジネス ルール エンジン (BRE) を実装する場合は、次の要因を検討してください。  
  
## <a name="fact-types"></a>ファクトの種類  
 ルール エンジンでは、アクセス .NET ファクトを時間と比較したアクセスの XML とデータベースのファクトにかかるが時間がかかりません。 ポリシーで、.NET、または XML、またはデータベース ファクトを使用して、選択した場合は、パフォーマンス向上のための .NET のファクトの使用を検討してください。  
  
## <a name="data-table-vs-data-connection"></a>データ接続とデータ テーブル  
 データ セットのサイズが小さい (< 10 程度)、 **TypedDataTable**バインドよりも優れたパフォーマンスを提供する、 **DataConnection**バインドします。 ただし、 **DataConnection**バインディングがパフォーマンスが向上しますよりも、 **TypedDataTable**データ セットが大きいときにバインディング (10 以上の行数約)。 そのため、使用するかどうかを決定する必要があります、 **DataConnection**バインドまたは**TypedDataTable**データ セットの推定サイズに基づいて、バインドします。  
  
## <a name="fact-retrievers"></a>ファクト取得コンポーネント  
 ファクト取得コンポーネントは、通常は、ポリシーが実行される前に、ルール エンジンへの長期的および緩やかに変化するファクトを指定に使用する標準的なメソッドを実装します。 エンジンは、これらのファクトをキャッシュし、複数の実行サイクルでそれらを使用します。 静的または比較的静的なファクトたびに、ルール エンジンを呼び出すことを送信するのではなく、最初に、という事実を送信し、必要な場合にのみメモリ内のファクトを更新するファクト取得コンポーネントを作成してください。  
  
## <a name="rule-priority"></a>ルールの優先順位  
 ルールの右辺でも左辺でも範囲の優先度設定**0**、大きい数値が高い優先順位とします。 アクションは、最高の優先度から最も低い優先順位の順序で実行されます。 使用して、ポリシーが順行連鎖の動作を実装するときに**Assert/update**優先順位の設定を使用して呼び出しをチェーンを最適化することができます。 たとえば、ある**Rule2**によって設定された値に依存している**Rule1**します。 提供**Rule1**優先度が高いことを意味**Rule2**以降後は実行のみ**Rule1**が起動し、値を更新します。 逆に場合、 **Rule2**がより高い優先度を指定するには、でした、1 回実行し、後にもう一度起動し、 **Rule1**が起動し、ファクトを更新する**Rule2**条件を使用して。 正しい結果が提供することがあります、与える**Rule1**このシナリオでは優先順位の高いより優れた性能が提供されます。  
  
## <a name="update-calls"></a>更新プログラムの呼び出し  
 Update 関数はにより更新されたファクトを使用していて、再評価するすべてのルールです。 Update 関数の呼び出しは、ファクトを更新するときに、大規模な一連のルールが再評価される場合に特に高価なできます。 この動作を回避できる場合があります。 たとえば、次の規則があるとします。  
  
 **Rule1:**  
  
```  
IF PurchaseOrder.Amount > 5   
THEN StatusObj.Flag = true; Update(StatusObj)  
```  
  
 **Rule2:**  
  
```  
IF PurchaseOrder.Amount <= 5   
THEN StatusObj.Flag = false; Update(StatusObj)  
```  
  
 ポリシーの使用の残りのルール**StatusObj.Flag**条件。 そのため、 **Update**で呼び出される、 **StatusObj**オブジェクトのすべてのルールが再評価されます。 任意の値、**量**フィールドは、すべてのルールを除く**Rule1**または**Rule2**が 2 回、評価前に 1 回、**更新**を呼び出す後に 1 回、 **Update**呼び出します。  
  
 関連付けられているを軽減するオーバーヘッド、する可能性がありますの値を設定、**フラグ**フィールドを**false**しを使用してのみ、ポリシーを呼び出す前に**Rule1**フラグを設定するポリシー. この場合、 **Update**場合にのみが呼び出されますの値、**量**フィールドが 5 より大きい、 **Update**場合、関数は呼び出されませんの値**量**が 5 未満。 そのため、すべてのルールを除く**Rule1**または**Rule2**評価される場合にのみ 2 回の値、**量**フィールドが 5 より大きい。  
  
## <a name="usage-of-logical-or-operators"></a>論理 OR 演算子の使用状況  
 論理 OR 演算子の増加を条件で使用すると、順列が追加されてルール エンジンの分析ネットワークが拡大が作成されます。 パフォーマンスの観点からは論理 OR 演算子を含まないアトミック ルールに条件を分割することをお勧めします。  
  
## <a name="caching-settings"></a>キャッシュの設定  
 ルール エンジンは、2 つのキャッシュを使用します。 1 つ目は更新サービスによって使用され、2 つ目は各 BizTalk プロセスによって使用されます。 ポリシーを使用すると、最初に、BizTalk プロセスは、update サービスからのポリシー情報を要求します。 更新サービス、ルール エンジン データベースからポリシー情報を取得するには、それをキャッシュおよび BizTalk プロセスに情報を返します。 BizTalk プロセスは、その情報に基づいて、ポリシー オブジェクトを作成し、関連付けられているルール エンジン インスタンスには、ポリシーの実行が完了すると、ポリシー オブジェクトをキャッシュに格納します。 同じポリシーが再び呼び出されたときがある場合、BizTalk プロセス ポリシー オブジェクトをキャッシュから再利用します。 同様に、BizTalk プロセスは、update サービスからのポリシーに関する情報を要求、使用できる場合、更新サービスはポリシーについては、キャッシュにします。 60 秒ごとに、更新サービスもチェック加えられていないかどうか、データベース内のポリシーを更新します。 すべての更新プログラムがある場合は、更新サービスが情報を取得し、更新された情報をキャッシュします。  
  
 これらのキャッシュに関連するルール エンジンは、次の 3 つのチューニング パラメーターは。**CacheEntries**、 **CacheTimeout**、および**PollingInterval**します。 レジストリまたは構成ファイルでは、これらのパラメーター値を指定できます。 値、 **CacheEntries**パラメーターは、キャッシュ内のエントリの最大数、既定で 32 の値に設定されます。 値を大きくことも、 **CacheEntries**パラメーターを特定のシナリオでパフォーマンスが向上します。 たとえば、繰り返し; 40 個のポリシーを使用しています。値を大きくことができます、 **CacheEntries**パフォーマンスを向上させるために 40 パラメーター。 キャッシュの詳細の最大メモリの 40 のポリシーを維持するために、更新サービスをこのようにするとします。  
  
 値**CacheTimeout**時間のエントリは、更新サービス キャッシュに保持されている秒数。 つまり、 **CacheTimeout**から参照せず、ポリシーをキャッシュに保持するために、値がどのくらいの時間、キャッシュ エントリを参照します。 既定値**CacheTimeout**パラメーターは 3600 秒、つまり 1 時間です。 キャッシュ エントリが 1 時間以内に参照されていない場合、エントリが削除されることを意味します。 場合によってでの値を大きく場合があります、 **CacheTimeout**パフォーマンスを向上させるためにパラメーター。 たとえば、2 時間ごと、ポリシーが呼び出される場合、ポリシーの実行のパフォーマンスが改善を増やすことで、 **CacheTimeout**パラメーター値を 2 時間よりも大きくします。  
  
 **PollingInterval**パラメーターのルール エンジン更新サービスの更新プログラムのルール エンジン データベースを確認する秒単位で時間を定義します。 既定値、 **PollingInterval**パラメーターは 60 秒です。 ポリシーがまったくは更新されないか、めったに更新されますがわかっている場合は、パフォーマンスを向上させるために大きな値にこのパラメーターを変更できます。  
  
## <a name="sideeffects-property"></a>SideEffects プロパティ  
 **ClassMemberBinding**、 **DatabaseColumnBinding**、および**XmlDocumentFieldBinding**クラスという名前のプロパティがある**SideEffects**. このプロパティは、バインドされるフィールド、メンバー、または列の値がキャッシュされているかどうかを決定します。 既定値、 **SideEffects**プロパティ、 **DatabaseColumnBinding**と**XmlDocumentFieldBinding**クラスは**false**. 既定値、 **SideEffects**プロパティ、 **ClassMemberBinding**クラスは**true**します。 そのため、XML ドキュメントのフィールドまたはデータベース テーブルの列に 2 回目またはポリシー内で後でアクセス、その値がキャッシュから取得します。 ただし、2 回目またはそれ以降、.NET オブジェクトのメンバーがアクセスされるは、値とキャッシュではなく、.NET オブジェクトから取得されます。 設定、 **SideEffects**プロパティは、.NET の**ClassMemberBinding**に**false**フィールドの値がキャッシュから取得されるので、パフォーマンスが向上します2 回目以降。 できますのみこのプログラムで実行します。 ビジネス ルール作成ツールを公開しません、 **SideEffects**プロパティ。  
  
## <a name="instances-and-selectivity"></a>Instances と selectivity  
 **XmlDocumentBinding**、 **ClassBinding**、および**DatabaseBinding**クラスがある 2 つのプロパティ。**インスタンス**と**選択度**します。 インスタンスの値は、作業メモリ内のクラスのインスタンスの予期される数です。 値**選択度**ルールの条件が正常に渡すクラスのインスタンスの割合を指定します。 ルール エンジンでは、これらの値を使ってように最小限のインスタンスが最初に条件の評価に使用され、残っているインスタンスを使用して、条件の評価を最適化します。 オブジェクトのインスタンスの数に関する予備知識があれば、設定、**インスタンス**プロパティの値をパフォーマンスが向上します。 同様に、これらのオブジェクトの条件を渡すことの割合の知識があれば、設定、**選択度**プロパティの値をパフォーマンスが向上します。 プログラムでのみこれらのパラメーター値を設定することができます。 ビジネス ルール作成ツールはそれらを公開しません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)
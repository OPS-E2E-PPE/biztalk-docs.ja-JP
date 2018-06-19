---
title: 同時実行プログラムに対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbc40e4c-d5a1-4763-9683-09a744e5b656
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bd7aae5d90c85e913c0e65a20f1d03e81c526e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218314"
---
# <a name="operations-on-concurrent-programs"></a>同時実行プログラムでの操作
操作として Oracle E-business Suite での同時実行プログラムが表示された[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。  Oracle アプリケーションに固有の同時実行プログラムと共に、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]も次の 3 つの標準的な操作を明らか: Get_Status、Wait_For_Request、および Submit_Request です。 これは、Oracle アプリケーションに 2 つの同時実行プログラムがある場合は、5 つの操作が公開することを意味します。 各の同時実行プログラム、および標準的な操作の 3 つのいずれか。  
  
 詳細については。  
  
-   参照と同時実行のプログラムの検索を参照してください。[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
-   同時実行プログラムを起動する方法、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite を使用して BizTalk Server での同時実行プログラムの起動](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)です。  
  
> [!IMPORTANT]
>  同時実行プログラムでのアプリケーションのコンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]同時実行プログラムでその操作を実行する前にします。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定、およびアイテムのアクセス制御を設定して Oracle E-business Suite でセキュリティ保護されたトランザクションを容易にするためです。 アプリケーションのコンテキスト、およびように設定する方法については、アプリケーション コンテキストの設定を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
 次のセクションでは、によって公開される操作に関する情報を提供する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の同時実行プログラムです。  
  
##  <a name="Concurrent"></a>< Concurrent_Program_Name > の操作  
 前述のように、Oracle アプリケーションの同時実行プログラムの数と同じ数の < Concurrent_Program_Name > 操作があります。 < Concurrent_Program_Name > 操作が 5 つの標準的なパラメーターを受け取る: 複合型および単純型の 2 つの 3 つです。  
  
> [!NOTE]
>  そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。 これらの同時実行プログラムを正常に呼び出すには、ユーザーは、値を必要とする同時実行プログラムのパラメーターを確認する Oracle E-business Suite のマニュアルを参照され、それらを指定する必要があります。 このような同時実行プログラムの例は**Journal インポート**(実際の名前: **GLLEZL**) で、**元帳**アプリケーションです。  
  
 **複合型パラメーター**  
  
-   **SetOptions**: 要求を送信する前に、同時実行プログラムのオプションを設定することができます。 SetOptions は、パラメーターとして、次のオプションを取ります。  
  
    -   **暗黙的な**: Oracle E-business Suite でのユーザーの同時要求の形式で、同時要求を表示するかどうかを示します。 次の 4 つの値のいずれかを指定できます:**いいえ**、**はい**、**エラー**または**警告**です。 指定する**いいえ**Oracle E-business Suite でのユーザーの同時要求フォームに表示される要求。 指定する**はい**システム管理者の特権を持つ同時要求のフォームからのみ要求を表示できることを意味します。 指定する**エラー**が失敗した場合にのみ、ユーザーの同時要求のフォームに表示される要求が発生します。 指定する**警告**要求ユーザーの同時要求フォーム場合にのみの表示があることを指定すると、警告またはエラー。  
  
    -   **保護されている**: Oracle E-business Suite での同時要求フォームを使用して行われる更新に対する同時要求が保護されているかどうかを示します。 指定できます**はい**(保護) または**いいえ**(保護されていない)。  
  
    -   **言語**: サポート NLS (National Language) の言語を示します。 値が指定されていない場合の既定値は、現在の言語です。  
  
    -   **Territory**: 言語の販売区域を示します。 値が指定されていない場合の既定値は現在の言語の販売区域です。  
  
    -   **ContinueOnFail**: 同時実行要求の送信を続行するかの場合は例外をスローするかどうかを示す**SetOptions**は失敗します。 指定できます**True** (続行) または**False** (例外をスローする)。  
  
-   **SetPrintOptions**: 要求を送信する前に、同時実行プログラムの印刷オプションを設定することができます。 SetPrintOptions は、パラメーターとして、次のオプションを取ります。  
  
    -   **プリンター**: 同時要求の出力を送信するプリンター名を示します。 Oracle E-business Suite で同時実行プログラム形式で既に設定されている場合は、この印刷オプションをオーバーライドすることはできません。  
  
    -   **スタイル**: 同時要求の出力に使用される印刷スタイルを示します。 たとえば、印刷の向きを指定できます (**ランドス ケープ**または**縦**)。 印刷スタイルが Oracle E-business Suite で同時実行プログラム形式で既に設定されている場合、**ために必要なスタイル** チェック ボックスが選択されている場合、この印刷オプションをオーバーライドすることはできません。  
  
    -   **コピー**: 同時要求の出力の印刷するコピーの数を示します。  
  
    -   **SaveOutput**: 出力ファイルを保存するかどうかを示します。 指定できます**はい**または**いいえ**です。  
  
    -   **PrintTogether**: サブ要求を含むこれらの要求にのみ適用されます。 サブ要求の出力を印刷する方法を示します。 指定した場合**Y**、サブ要求の出力がすべてのサブ要求が完了した後のみです。 指定した場合**N**、各サブ要求の出力が完了するとします。  
  
    -   **ContinueOnFail**: 同時実行要求の送信を続行するかの場合は例外をスローするかどうかを示す**SetPrintOptions**は失敗します。 指定できます**True** (続行) または**False** (例外をスローする)。  
  
-   **SetRepeatOptions**: 要求を送信する前にプログラムを同時に繰り返しオプションを設定することができます。 **SetRepeatOptions**パラメーターとして、次のオプションを取得します。  
  
    -   **RepeatTime**: 同時実行要求を繰り返すには 1 日の時刻を示します。  
  
    -   **RepeatInterval**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 再送信を要求の間の間隔を示します。 このオプションと共に使用して**RepeatUnit**の再送信の間の時間を指定します。  
  
    -   **RepeatUnit**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 と共に使用する時間の単位**RepeatInterval**を再送信を要求の間の時間を指定します。 指定できます**分**、**時間**、**日数**または**月**です。  
  
    -   **RepeatType**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 同時要求の実行の"start"、後または同時要求の実行"end"の後ろに、繰り返しの間隔を適用するかどうかを示します。  
  
    -   **RepeatEndTime**: 同時実行の要求を再送信を停止する日付と時刻を示します。  
  
    -   **ContinueOnFail**: 同時実行要求の送信を続行するかの場合は例外をスローするかどうかを示す**SetRepeatOptions**です。 指定できます**True** (続行) または**False** (例外をスローする)。  
  
 **単純型のパラメーター**  
  
-   **説明**: 同時要求の説明。  
  
-   **StartTime**: 同時要求の実行開始時刻を示します。  
  
## <a name="getstatus-operation"></a>Get_Status 操作  
 Get_Status、標準的な操作は、要求のフェーズ/状態と同時実行プログラムの完了のメッセージを返します。 この操作は同時実行プログラムの要求 ID を受け取り (**RequestID**) を入力としてし、次の情報を返します。  
  
-   **フェーズ**: FND_LOOKUPS からわかりやすい要求フェーズ。  
  
-   **ステータス**: FND_LOOKUPS からのユーザー フレンドリな要求の状態。  
  
-   **DevPhase**: プログラム ロジックの比較に使用できる文字列としての要求フェーズ。  
  
-   **DevStatus**: プログラム ロジックの比較に使用できる文字列として、要求の状態。  
  
-   **メッセージ**: 完了のメッセージ、要求が完了した場合。  
  
## <a name="waitforrequest-operation"></a>Wait_For_Request 操作  
 標準の操作では、Wait_For_Request は、要求の完了を待機し、要求フェーズ/状態と、完了メッセージを返します。 この操作は同時実行プログラムの要求 ID を受け取り (**RequestID**) を確認するまで待機する秒数 (**間隔**)、および要求の完了 (まで待機する秒単位で最大の時間**MaxWait**) の入力パラメーターとしてし Get_Status 操作と同様に、同じ情報を返します。  
  
## <a name="submitrequest-operation"></a>Submit_Request 操作  
 標準の操作では、Submit_Request は、同時実行マネージャーによって処理するための同時要求を送信します。 要求が正常に完了するは、この操作は、同時要求 ID でを返します。 それ以外の場合、「0」を返します。  
  
 Submit_Request 操作は 6 つの標準的なパラメーターを受け取ります。 複合型の単純型の 3 つ各します。 別に、これらのパラメーターも受け取ります同時実行プログラムの引数として文字列の配列。  
  
 **複合型パラメーター**  
  
 Submit_Request 操作にかかる**SetOptions**、 **SetPrintOptions**、および**SetRepeatOptions**入力パラメーターとして。 これらのパラメーターについては、次を参照してください。 [ &lt;Concurrent_Program_Name&gt;操作](#Concurrent)このセクションで前述しました。  
  
 **単純型のパラメーター**  
  
-   **プログラム**: 要求の送信を同時実行プログラムの短い名前。  
  
-   **説明**: 同時要求の説明。  
  
-   **StartTime**: 同時要求の実行開始時刻。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
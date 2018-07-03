---
title: 同時実行プログラムに対する操作 |Microsoft Docs
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
ms.openlocfilehash: a07e1cb6597a90687865932fcd2d2ce7e0e476af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000001"
---
# <a name="operations-on-concurrent-programs"></a>同時実行プログラムに対する操作
Oracle E-business Suite での同時実行プログラムでの操作として表示された[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。  Oracle アプリケーションに固有の同時実行プログラムと共に、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の 3 つの標準的な操作も明らかになります: Get_Status、Wait_For_Request、および Submit_Request します。 これは、Oracle アプリケーションに 2 つの同時実行プログラムがある場合は、5 つの操作が公開することを意味します。 1 つは、各同時実行プログラム、3 つの標準的な操作。  
  
 詳細については。  
  
- 参照および検索の同時実行プログラムを参照してください。[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  
  
- 同時実行プログラムを呼び出す方法、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite を使用して BizTalk Server での同時実行のプログラムを呼び出す](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)します。  
  
> [!IMPORTANT]
>  同時実行プログラムでのアプリケーション コンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]同時実行プログラムで操作を実行する前にします。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定とアーティファクトのアクセス制御を設定して Oracle E-business Suite でセキュリティで保護されたトランザクションを促進するためです。 アプリケーションのコンテキスト、および設定する方法については、アプリケーション コンテキストの設定を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
 次のセクションでは、によって公開される操作に関する情報を提供する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の同時実行プログラム。  
  
##  <a name="Concurrent"></a> < Concurrent_Program_Name > の操作  
 前述のように、多くの < Concurrent_Program_Name > 操作として、Oracle アプリケーションで同時実行プログラムの数があります。 < Concurrent_Program_Name > 操作が 5 つの標準パラメーターを受け取ります。 3 つの複合型および単純型の 2 つです。  
  
> [!NOTE]
>  そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。 これらの同時実行プログラムを正常に呼び出すは、ユーザーは、値を必要とする同時実行プログラムのパラメーターを把握する Oracle E-business Suite のドキュメントを参照して、それらを指定する必要があります。 このような同時実行プログラムの例は、 **Journal インポート**(実際の名前: **GLLEZL**) で、**総勘定元帳**アプリケーション。  
  
 **複合型のパラメーター**  
  
- **SetOptions**: 要求を送信する前に、同時実行プログラムのオプションを設定することができます。 SetOptions はパラメーターとして、次のオプションを受け取ります。  
  
  -   **暗黙的な**: Oracle E-business Suite でのユーザーの同時要求の形式で同時要求を表示するかどうかを示します。 次の 4 つの値のいずれかを指定することができます:**いいえ**、**はい**、**エラー**または**警告**します。 指定する**いいえ**場合、要求は、Oracle E-business Suite でのユーザーの同時要求の形式で表示されます。 指定する**はい**システム管理者の特権の同時要求のフォームからのみ、要求を表示できることを意味します。 指定する**エラー**失敗した場合にのみ、ユーザーの同時要求の形式で表示する要求。 指定する**警告**警告またはエラーがあること、ユーザーの同時要求フォームのみの場合に表示する要求を発生します。  
  
  -   **保護されている**: Oracle E-business Suite での同時要求フォームを使用して行われる更新に対する同時要求が保護されているかどうかを示します。 指定できます**はい**(保護) または**いいえ**(保護されていない)。  
  
  -   **言語**: 各国語サポート (NLS) の言語を示します。 値が指定されていない場合の既定値は現在の言語です。  
  
  -   **Territory**: 言語の販売区域を示します。 値が指定されていない場合は、現在の言語の販売区域に既定値です。  
  
  -   **ContinueOnFail**: 同時要求を送信する必要があります続行またはケースで例外をスローするかどうかを示す**SetOptions**は失敗します。 指定できる**True** (続行) または**False** (例外をスロー)。  
  
- **SetPrintOptions**: 要求を送信する前に、同時実行プログラムの印刷オプションを設定することができます。 SetPrintOptions はパラメーターとして、次のオプションを受け取ります。  
  
  -   **プリンター**: 同時要求の出力を送信するプリンター名を示します。 Oracle E-business Suite での同時実行プログラムの形式で既に設定されている場合は、この印刷オプションをオーバーライドすることはできません。  
  
  -   **スタイル**: 印刷スタイル、同時要求の出力に使用されることを示します。 たとえば、印刷の向きを指定できます (**ランドス ケープ**または**縦**)。 Oracle E-business suite での同時実行プログラムのフォームで既に印刷スタイルを設定する場合、**ために必要なスタイル** チェック ボックスが選択されている場合、この印刷オプションをオーバーライドすることはできません。  
  
  -   **コピー**: 同時要求の出力の印刷するコピーの数を示します。  
  
  -   **SaveOutput**: 出力ファイルを保存するかどうかを示します。 指定できます**はい**または**いいえ**します。  
  
  -   **PrintTogether**: サブ要求が含まれているそれらの要求にのみ適用できます。 サブ要求の出力を印刷する方法を示します。 指定した場合**Y**、サブのすべての要求が完了した後にのみ、サブ要求の出力が出力されます。 指定した場合**N**、完了すると、各サブ要求の出力が出力されます。  
  
  -   **ContinueOnFail**: 同時要求を送信する必要があります続行またはケースで例外をスローするかどうかを示す**SetPrintOptions**は失敗します。 指定できる**True** (続行) または**False** (例外をスロー)。  
  
- **SetRepeatOptions**: 要求を送信する前に、同時実行プログラムの繰り返しのオプションを設定することができます。 **SetRepeatOptions**パラメーターとして、次のオプションには。  
  
  -   **RepeatTime**: 時間帯を同時要求を繰り返すことを示します。  
  
  -   **RepeatInterval**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 要求の再送信間隔を示します。 と共にこのオプションを使用して**RepeatUnit**を再送信間隔を指定します。  
  
  -   **RepeatUnit**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 と一緒に使用すると時間の単位**RepeatInterval**を再送信を要求の間の時間を指定します。 指定できます**分**、**時間**、**日**または**か月間**します。  
  
  -   **RepeatType**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 繰り返しの間隔が、同時要求の実行"end"または"start"個の同時要求の実行後に適用されるかどうかを示します。  
  
  -   **RepeatEndTime**: 同時実行要求を再送信を停止する日付と時刻を示します。  
  
  -   **ContinueOnFail**: 同時要求を送信する必要があります続行またはケースで例外をスローするかどうかを示す**SetRepeatOptions**します。 指定できる**True** (続行) または**False** (例外をスロー)。  
  
  **単純型のパラメーター**  
  
- **説明**: 同時実行の要求の説明。  
  
- **StartTime**: 同時実行の要求の実行開始時刻を示します。  
  
## <a name="getstatus-operation"></a>Get_Status 操作  
 標準の操作では、Get_Status には、要求フェーズ/状態と同時実行プログラムの完了メッセージが返されます。 この操作は同時実行プログラムの要求 ID を受け取り (**RequestID**)、入力として、次の情報を返します。  
  
-   **フェーズ**: FND_LOOKUPS からの要求のわかりやすいフェーズ。  
  
-   **ステータス**: FND_LOOKUPS からの要求のわかりやすい状態です。  
  
-   **DevPhase**: プログラム ロジックの比較に使用できる文字列として要求フェーズ。  
  
-   **DevStatus**: プログラム ロジックの比較に使用できる文字列として、要求の状態。  
  
-   **メッセージ**: 要求が完了した場合、完了メッセージ。  
  
## <a name="waitforrequest-operation"></a>Wait_For_Request 操作  
 標準の操作では、Wait_For_Request は、要求の完了するまで待機し、要求フェーズ/状態と完了メッセージを返します。 この操作は同時実行プログラムの要求 ID を受け取り (**RequestID**)、間隔のチェックを待機する秒数 (**間隔**)、および要求の完了 (を待機する秒単位で最大の時間**MaxWait**)、入力パラメーターとして Get_Status 操作のように、同じ情報を返します。  
  
## <a name="submitrequest-operation"></a>Submit_Request 操作  
 標準の操作では、Submit_Request は、同時実行マネージャーによって処理するための同時要求を送信します。 要求が正常に完了すると、この操作は同時実行の要求 ID を返します それ以外の場合、「0」を返します。  
  
 Submit_Request 操作は 6 つの標準パラメーターを受け取ります。 複合型の単純型の 3 つそれぞれします。 別に、これらのパラメーターはこれも、文字列の配列として同時実行プログラムの引数を受け取ります。  
  
 **複合型のパラメーター**  
  
 Submit_Request 操作にかかる**SetOptions**、 **SetPrintOptions**、および**SetRepeatOptions**入力パラメーターとして。 これらのパラメーターについては、次を参照してください。 [ &lt;Concurrent_Program_Name&gt;操作](#Concurrent)このセクションで前述しました。  
  
 **単純型のパラメーター**  
  
-   **プログラム**: 要求の送信を同時実行プログラムの短い名前。  
  
-   **説明**: 同時実行の要求の説明。  
  
-   **StartTime**: 同時実行の要求の実行開始時刻。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
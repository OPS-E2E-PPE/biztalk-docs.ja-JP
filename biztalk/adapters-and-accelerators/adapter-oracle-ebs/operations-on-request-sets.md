---
title: 要求のセットに対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0537354d-821e-4cf9-a4d1-f4e7d1643df9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8051a94df28df4090f78287070c5143e6f866ed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217298"
---
# <a name="operations-on-request-sets"></a>要求のセットに対する操作
Oracle E-business Suite で設定要求は、一連のレポートとは、さまざまな段階に分類する同時実行プログラムです。 設定を一連のレポートと同時実行プログラムを実行する 1 つの要求を使用することができます。 セットは、1 つまたは複数の段階的に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 を要求します。 これらのステージが、互いにリンクされている、各ステージの実行の順序が定義されます。 要求のセットに関する Oracle 固有の詳細についてを参照してください[http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539)です。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite で要求のセットを実行できます。 要求セットでの操作として公開される、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 要求セットには、同時実行プログラムのセットが含まれている、ので、要求操作のセットの同時実行プログラム、入力パラメーターです。 同時実行のプログラムと共に要求セットの操作は 4 つの複合型のパラメーターおよび単純型のパラメーターを入力として取得します。  
  
> [!IMPORTANT]
>  要求のセットは、アプリケーションのコンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットに対するすべての操作を実行する前にします。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定、およびアイテムのアクセス制御を設定して Oracle E-business Suite でセキュリティ保護されたトランザクションを容易にするためです。 アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="complex-type-parameters"></a>複合型パラメーター
  
-   **SetRelClassOptions**: 要求セットのスケジュールのオプションを設定することができます。 SetRelClassOptions と SetRepeatOptions の両方が設定されている場合、SetRelClassOptions が優先されます。 SetRelClassOptions は、パラメーターとして、次のオプションを取ります。  
  
    -   **アプリケーション**: 要求セットに関連付けられているアプリケーションの短い名前を示します。  
  
    -   **ClassName**: 要求セットに関連付けられているクラスの名前を示します。  
  
    -   **CanceOrHold**: キャンセルまたは保留中フラグを示します。  
  
    -   **StaleDate**: 日付を示す要求セットがまだ実行されていない場合以降にこの要求のセットが取り消されます。  
  
    -   **ContinueOnFail**: 要求セットの送信を続行するか SetRelClassOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定できます (続行) または"False"(から例外をスローする)。  
  
-   **SetPrintOptions**: 要求セットの印刷オプションを設定することができます。 SetPrintOptions は、パラメーターとして、次のオプションを取ります。  
  
    -   **プリンター**: 出力設定要求を送信するプリンター名を示します。  
  
    -   **スタイル**: 出力設定要求の印刷に使用される印刷スタイルを示します。 たとえば、向き (横 (「)」または「縦」) を指定できます。  
  
    -   **コピー**: 出力設定要求の印刷するコピーの数を示します。  
  
    -   **SaveOutput**: 出力ファイルを保存するかどうかを示します。 "True"または"False"を指定することができます。  
  
    -   **PrintTogether**: サブ要求に対してのみ該当します。 サブ要求の出力を印刷する方法を示します。 "Y"を指定すると、すべてのサブ要求が完了した後にのみ、サブ要求の出力が印刷されます。 指定した場合を完了したときに"N"、各サブ要求の出力を出力します。  
  
    -   **ContinueOnFail**: 要求セットの送信を続行するか SetPrintOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定できます (続行) または"False"(から例外をスローする)。  
  
-   **SetRepeatOptions**: 要求セットの繰り返しオプションを設定することができます。 SetRepeatOptions は、パラメーターとして、次のオプションを取ります。  
  
    -   **RepeatTime**: 要求のセットを繰り返すには 1 日の時刻を示します。  
  
    -   **RepeatInterval**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 再送信を要求の間の間隔を示します。 このオプションと共に使用して**RepeatUnit**の再送信の間の時間を指定します。  
  
    -   **RepeatUnit**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 と共に使用する時間の単位**RepeatInterval**を再送信を要求の間の時間を指定します。 "Minutes"、"Hours"、"Days"または"Months"を指定することができます。  
  
    -   **RepeatType**: このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 セットの実行を前の要求の"start"後または前の要求の"end"セットの実行後に繰り返しの間隔を適用するかどうかを示します。  
  
    -   **RepeatEndTime**: 要求のセットを再送信を停止する日付と時刻を示します。  
  
    -   **ContinueOnFail**: 要求セットの送信を続行するか SetRepeatOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定できます (続行) または"False"(から例外をスローする)。  
  
-   **SetNlsOptions**: 要求セットの NLS オプションを設定することができます。 SetNlsOptions は、パラメーターとして、次のオプションを取ります。  
  
    -   **言語**: NLS 言語を示します。  
  
    -   **言語**: 言語の販売区域を示します。  
  
    -   **ContinueOnFail**: 要求セットの送信を続行するか SetNlsOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定できます (続行) または"False"(から例外をスローする)。  
  
## <a name="simple-type-parameter"></a>単純型のパラメーター
  
 **StartTime**: 要求セットの実行開始時刻を示します。  
  
 場合は、要求設定が正常に完了、同時実行要求 ID が返されます。 それ以外の場合、「0」が返されます。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
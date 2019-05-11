---
title: 要求セットに対する操作 |Microsoft Docs
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
ms.openlocfilehash: cfc8c773be09a302e740b2eb7d59828e3a1688b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375293"
---
# <a name="operations-on-request-sets"></a>要求セットに対する操作
Oracle E-business Suite で設定要求は、一連のレポートとはさまざまな段階に分かれていますが、同時実行プログラムです。 一連のレポートと同時実行プログラムを実行する 1 つの要求を使用することができます。 要求セットは 1 つまたは複数の段階に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 します。 これらのステージは互いにリンクされ、各ステージの実行の順序が定義されています。 要求のセットに関する Oracle 固有の詳細を参照してください[ http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539)します。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite での要求セットを実行できます。 操作として公開される要求セット、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 要求セットには、同時実行プログラムのセットが格納されている、ため、要求の設定操作の同時実行プログラムは入力パラメーターです。 同時実行のプログラムと共に要求の設定操作は 4 つの複合型パラメーターおよび単純型のパラメーターを入力として取得します。  
  
> [!IMPORTANT]
>  要求のセット、アプリケーションのコンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットの任意の操作を実行する前にします。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定とアーティファクトのアクセス制御を設定して Oracle E-business Suite でセキュリティで保護されたトランザクションを促進するためです。 アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
## <a name="complex-type-parameters"></a>複合型のパラメーター
  
-   **SetRelClassOptions**:要求セットのスケジュールのオプションを設定できます。 SetRelClassOptions と SetRepeatOptions の両方が設定されている場合、SetRelClassOptions が優先されます。 SetRelClassOptions はパラメーターとして、次のオプションを受け取ります。  
  
    -   **アプリケーション**:要求セットに関連付けられたアプリケーションの短い名前を示します。  
  
    -   **ClassName**:要求セットに関連付けられたクラスの名前を示します。  
  
    -   **CanceOrHold**:キャンセル または 保留のフラグを示します。  
  
    -   **StaleDate**:日時を示す要求セットがまだ実行していない場合、または後にこの要求セットがキャンセルされます。  
  
    -   **ContinueOnFail**:要求セットを送信する必要があります続行または SetRelClassOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定することができます (引き続き) または"False"(例外をスローする)。  
  
-   **SetPrintOptions**:要求セットの印刷オプションを設定できます。 SetPrintOptions はパラメーターとして、次のオプションを受け取ります。  
  
    -   **プリンター**:出力を設定する要求を送信するプリンター名を示します。  
  
    -   **スタイル**:出力設定要求の印刷に使用する印刷スタイルを示します。 たとえば、(「Landscape」または「Portrait」) の方向を指定できます。 します  
  
    -   **コピー**:出力設定要求の印刷するコピーの数を示します。  
  
    -   **SaveOutput**:出力ファイルを保存するかどうかを示します。 "True"または"False"を指定することができます。  
  
    -   **PrintTogether**:サブ要求に対してのみ適用されます。 サブ要求の出力を印刷する方法を示します。 "Y"を指定すると、すべてのサブ要求が完了した後にのみ、サブ要求の出力が印刷されます。 指定した場合は、これが完了すると、"N"、各サブ要求の出力が出力されます。  
  
    -   **ContinueOnFail**:要求セットを送信する必要があります続行または SetPrintOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定することができます (引き続き) または"False"(例外をスローする)。  
  
-   **SetRepeatOptions**:要求セットの繰り返しのオプションを設定できます。 SetRepeatOptions はパラメーターとして、次のオプションを受け取ります。  
  
    -   **RepeatTime**:時間帯を要求のセットを繰り返すことを示します。  
  
    -   **RepeatInterval**:このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 要求の再送信間隔を示します。 と共にこのオプションを使用して**RepeatUnit**を再送信間隔を指定します。  
  
    -   **RepeatUnit**:このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 と一緒に使用すると時間の単位**RepeatInterval**を再送信を要求の間の時間を指定します。 "Minutes"、"Hours"、"Days"または「月」を指定することができます。  
  
    -   **RepeatType**:このパラメーターは場合にのみ適用**RepeatTime**は NULL です。 前の要求の"start"が実行を設定した後、または前の要求の"end"が実行を設定した後、リピート間隔が適用されるかどうかを示します。  
  
    -   **RepeatEndTime**:要求のセットを再送信を停止する日付と時刻を示します。  
  
    -   **ContinueOnFail**:要求セットを送信する必要があります続行または SetRepeatOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定することができます (引き続き) または"False"(例外をスローする)。  
  
-   **SetNlsOptions**:要求セットの NLS オプションを設定できます。 SetNlsOptions はパラメーターとして、次のオプションを受け取ります。  
  
    -   **言語**:NLS 言語を示します。  
  
    -   **言語**:言語の販売区域を示します。  
  
    -   **ContinueOnFail**:要求セットを送信する必要があります続行または SetNlsOptions に失敗した場合に例外をスローするかどうかを示します。 "True"を指定することができます (引き続き) または"False"(例外をスローする)。  
  
## <a name="simple-type-parameter"></a>単純型のパラメーター
  
 **startTime**:要求セットの実行開始時刻を示します。  
  
 場合は、要求の設定が正常に完了、同時実行要求 ID が返されます。 それ以外の場合、「0」が返されます。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)
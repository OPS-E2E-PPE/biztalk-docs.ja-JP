---
title: 送信バッチの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75e6f41a-0e24-47bf-9234-125791c62044
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0413da7cb3d3dc328abbfd6916dd598b174244ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391358"
---
# <a name="configuring-an-outgoing-batch"></a>送信バッチの構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でトランザクション セットを EDI インターチェンジへバッチ処理する方法を定義するには、アグリーメントに対して 1 つ以上のバッチ構成を作成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でそのアグリーメントに関連付けられ、バッチのフィルター条件を満たすインターチェンジはすべて、そのバッチ構成の同じリリース条件に従ってバッチ処理されてリリースされます。  
  
 バッチ構成には、バッチ名、バッチ ID、フィルター定義、グループ定義、バッチ リリース条件、およびバッチ アクティベーション条件が含まれます。 すべてのプロパティとバッチに関連するオプションを利用できる、**バッチ構成**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 アグリーメントのバッチ構成を作成するを参照してください。 [(X12) をバッチ処理構成](../core/configuring-batching-x12.md)します。  
  
> [!NOTE]
>  バッチのドキュメント標準はアグリーメント プロパティ自体から確認されます。 たとえば、X12 メッセージ用のアグリーメントである場合、バッチのドキュメント標準は X12 になります。  
  
## <a name="batch-categories"></a>バッチ カテゴリ  
 上の右上隅にあるドロップダウン リストを使用して、**バッチ構成**ページを表示するどのバッチ構成を決定します。  
  
-   **[すべて]**: すべてのバッチ構成を表示します。  
  
-   **[アクティブ]**: アクティブなバッチ構成のみを表示します。  
  
-   **非アクティブな**:非アクティブなバッチ構成のみを表示します。  
  
## <a name="batch-identification"></a>バッチ識別子  
 バッチ ID には、バッチ名、説明、バッチ ID、およびバッチ処理オーケストレーション インスタンス ID が含まれます。  
  
### <a name="batch-name"></a>バッチ名  
 バッチ構成がで指定されたバッチ名に基づいて作成**バッチ構成**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 複数のバッチで同じ構成設定を共有できますが、一意のバッチ名が必要です。  
  
### <a name="batch-description"></a>バッチの説明  
 [バッチの説明] ボックスはバッチ構成の説明を示します。  
  
### <a name="batch-id"></a>バッチ ID。  
 バッチ ID がによって自動的に生成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で新しいバッチ構成を作成するときに、**バッチ構成**ページ。 この値は、特定のバッチ構成のバッチ フィルターに一致する受信インターチェンジを示す BatchMarker パイプライン コンポーネントにより使用されます。 また、この値は特定のバッチ構成と関連付けられたバッチ処理オーケストレーションのサブスクリプション フィルターとしても使用されます。  
  
### <a name="orchestration-instance-id"></a>オーケストレーション インスタンス ID  
 このバッチ構成に対してアクティブになったバッチ オーケストレーション インスタンスのオーケストレーション インスタンス ID です。  
  
## <a name="batch-filter"></a>バッチ フィルター  
 バッチで適用されるバッチ フィルタ定義に基づいて作成、**バッチ構成**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 このフィルターで、バッチ処理するトランザクション セットまたはメッセージを指定します。 このフィルターの値は、バッチ オーケストレーションのインスタンスがアクティブになっているときに変更できます。 フィルターを変更しても、バッチのリリース条件には影響しません。  
  
> [!NOTE]
>  アクティブなバッチのバッチ フィルターを変更した場合、この情報が Biztalk Server でキャッシュされ、新しいフィルター条件がアクティブになるまでに 15 分かかります。 この更新間隔は変更できません。  
> 
>  新しいフィルターをすぐにアクティブにする場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト プロセスを再開します。  
  
 送信バッチには、複数のグループを含めることができますが、トランザクションの種類ごとに含められるグループは 1 つだけです。 グループには、複数のトランザクション セットを含めることができますが、各トランザクション セットのトランザクションの種類が同じでなければなりません。  
  
 複数のバッチ構成で同じバッチ フィルターを共有できます。ドキュメントが複数のバッチ フィルターに一致する場合、ドキュメントは一致するすべてのバッチにルーティングされます。  
  
## <a name="group-definition"></a>グループ定義  
 バッチ出力内でのグループの構成方法は、アグリーメント プロパティの機能グループ ヘッダー (X12 の場合は GS、EDIFACT の場合は UNG) を定義することによって指定します。 グループは、X12 の場合はトランザクション セット識別コード (ST1)、EDIFACT の場合はメッセージの種類 (UNH2.1) と、バージョン、およびターゲットの名前空間に従って定義されます。 たとえば、1 つのインターチェンジに、1 つのメッセージの種類で構成される 1 つのグループと、別のメッセージの種類で構成されるもう 1 つのグループを含めることができます。 グループの構成の詳細については、次を参照してください。 [EDI プロパティを設定する](../core/configuring-edi-properties.md)します。  
  
> [!NOTE]
>  インターチェンジ内のグループの順序は定義されません。  
  
## <a name="batch-release-criteria"></a>バッチ リリース条件  
 バッチで設定された条件に従ってリリースされますが、**バッチ構成**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 バッチは、次のいずれかの方法でリリースできます。  
  
- スケジュール (時間単位、日単位、または週単位) に従って実行する。  
  
- グループで特定の数のトランザクション セットを使用できるときに実行する。  
  
- インターチェンジで特定の数のトランザクション セットを使用できるときに実行する。  
  
- バッチ処理で特定の数の文字を使用できるときに実行する。  
  
- 外部のアプリケーションによって外部トリガーが実行されると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
  選択した場合、**空のバッチ通知を送信**プロパティを**バッチ スケジュール**ダイアログ ボックスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージがない場合でも送信するバッチがスケジュールされているときに、空のバッチ メッセージを送信バッチ処理オーケストレーションで受信します。  
  
## <a name="batch-activation-criteria"></a>バッチ アクティベーション条件  
 バッチは、バッチ アクティベーション条件が満たされている場合にのみ、バッチ リリース条件に従ってリリースされます。 押す必要があります、オーケストレーションのインスタンスをアクティブ化する、**開始**ボタン、**バッチ構成**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 バッチ構成に対するオーケストレーションのインスタンスが作成されます。 場合、**開始**ボタンがクリックしてできる状態、バッチ構成に対するオーケストレーションのインスタンスが現在アクティブ化されていません。  
  
 キーを押す、**開始**ボタン、バッチのメッセージの収集は、次に該当する場合にのみ。  
  
- メッセージがバッチ フィルターの条件を満たしている。  
  
- 日付と時刻は、後で入力した日時が、**開始**フィールド。  
  
- 日付と時刻が前に入力した値には、**によって終了**フィールド、または、バッチ処理の数が小さいで出現回数、**終了までの発生回数**フィールド、または、 **終了日なし**オプションを選択します。 3 つすべてのオプションが 利用可能な**終了**セクション。  
  
  アクティベーション条件が設定されて、**バッチ構成**で一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
  した後、**開始**をバッチ処理オーケストレーションのインスタンスをアクティブ化 ボタンをについて説明した時間まで、メッセージをバッチの収集されませんが、**開始**プロパティが渡されます。  **バッチ構成** ページで、**をすぐに開始**が選択されていないと、**開始**クリックした日時より前の値に設定されているdatetime**開始**ボタン、バッチ処理オーケストレーションがアクティブとすぐが開始されます。 アクティベーションの日時が将来に設定されている場合は、その日時になるとバッチ処理が開始されます。  
  
  設定することができます、**開始**未来の datetime を指定する datetime。 ただしをクリックすると、**開始**ボタン、**開始**datetime は、今後は、オーケストレーション インスタンスはアクティブになりますが、[開始] 日時が発生するまでメッセージは収集されません。 BatchMarker パイプライン コンポーネントは、開始日の時刻になるまで、メッセージをルーティング オーケストレーションまたはバッチ処理オーケストレーションにルーティングするために必要なプロパティを昇格しません。 そのため、メッセージはバッチ処理されません。 しかし、そのメッセージをサブスクライブしている送信ポートまたはオーケストレーションによって、個別のメッセージとして取得されます。 BatchMarker パイプライン コンポーネントの動作の詳細については、次を参照してください。[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)します。  
  
## <a name="batch-termination-criteria"></a>バッチ終了条件  
 メッセージは後のバッチを収集しなくなります、**によって終了**datetime または後で出現回数、**終了までの発生回数**プロパティ。 バッチ処理オーケストレーションを非アクティブにしたくない場合は、選択、**終了日なし**オプション。  
  
> [!NOTE]
>  場合、**終了までの発生回数**プロパティを選択すると、空のバッチ通知はバッチ アクティベーションの範囲を終了するために必要な回数にカウントします。 通常であれば空のバッチ通知が送信される状態 (バッチ送信のスケジュールが設定されているものの、バッチ処理オーケストレーションでメッセージが受信されていない) が発生したが、空のバッチ通知が構成されていないために通知が送信されない場合にも、発生回数は加算されます。  
  
## <a name="see-also"></a>参照  
 [送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)
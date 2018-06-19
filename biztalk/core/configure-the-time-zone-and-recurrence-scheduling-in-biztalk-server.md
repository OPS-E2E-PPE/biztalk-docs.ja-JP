---
title: タイム ゾーンと BizTalk Server での定期的なスケジュールの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ab4cd85af0d15d7b089b106dc33aa77f1a10639
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497771"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a>タイム ゾーンと BizTalk Server での定期的なスケジュールを構成します。
タイム ゾーンを設定し、定期的なスケジュールを構成して受信場所で[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、受信場所の高度なスケジュールで、機能をいくつかのオプションが含まれています。 高度なオプションをスケジュールするには、タイム ゾーンを設定および定期的なスケジュールの設定も使用します。

このトピックでは、これらの機能を構成する方法を示します。

## <a name="prerequisites"></a>前提条件
インストール[Feature Pack 2](https://aka.ms/bts2016fp2)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。

## <a name="time-zone"></a>タイム ゾーン

**スケジュール**受信場所のプロパティが含まれています、**タイム ゾーン**プロパティです。 設定すると、受信場所で選択したタイム ゾーンはローカル コンピューターのタイム ゾーンの代わりに使用されます。 

すべての日付と時刻、**スケジュール**プロパティは、選択したタイム ゾーンに固有です。 任意の既存のスケジュールは、BizTalk 管理データベース (BizTalkMgmtDb) をホストしているサーバーのタイム ゾーンに移行されます。 

夏時間 (DST) の調整することもできます。 チェックすると、スケジュールは自動的に選択するタイム ゾーンの夏時間に調整されます。 このオプションには影響しません、スケジュール場合。

* 指定されたタイム ゾーンが夏時間を持たない
* 選択したタイム ゾーンの夏時間は発生しません

## <a name="enable-recurrence-schedule"></a>定期的なスケジュールを有効にします。
1. **BizTalk Server 管理コンソール**コンソールのいずれかを右クリックし、受信場所、および選択**プロパティ**です。 
2. **スケジュール**] ページで、[**有効にするサービス時間帯**です。 **開始時刻**と**停止時刻**スケジュールの実行が許可される最初の時間を設定します。

    ![サービス ウィンドウを有効にする受信ポート](../core/media/enable-service-windows-for-receive-port.PNG)

3. 追加のスケジュール オプションが表示されます。

    ![高度なスケジュールの受信ポート](../core/media/advanced-scheduling-for-receive-port.PNG)

4. **繰り返し**プロパティは、すべての日、週、または選択した月の受信ポートを実行します。 

    1. 使用して、**毎日**受信ポートを実行するには、定期的なアイテムすべて*x*の日数で開始、**から**選択した日付と内でのみ、**サービス ウィンドウ**を選択します。

        ![毎日のスケジュール](../core/media/daily-shcedule.png)

    2. 使用して、**毎週**受信ポートを 1 週間以内と内でのみ特定の日に実行するには、定期的なアイテム、**サービス時間帯**を選択します。 

        ![週単位のスケジュール](../core/media/weekly-shcedule.png)

    3. 使用して、**毎月**は毎月定期的に受信ポートを実行するには、定期的なアイテム。 **日数**と**で**オプションを使用できます。 
    
        使用して、**日数**内で特定の日付で、受信ポートを実行するには、定期的なアイテム、**月**を選択します。 

        ![月間スケジュールについて](../core/media/monthly-shcedule.PNG)

        使用して、**で**で月の特定の日に、受信ポートを実行するには、定期的なアイテム。

        ![スケジュールで毎月](../core/media/monthly-on-shcedule.PNG)

5. **[OK]** を選択して変更を保存します。 

## <a name="see-also"></a>参照
[この機能パックを構成します。](../core/configure-the-feature-pack.md)
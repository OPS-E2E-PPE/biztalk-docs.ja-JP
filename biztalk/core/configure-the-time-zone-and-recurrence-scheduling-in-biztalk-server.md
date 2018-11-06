---
title: タイム ゾーンと定期的なアイテムが BizTalk Server でスケジュール設定の構成 |Microsoft Docs
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
ms.openlocfilehash: fe12e4fe81705d178520f02591f8179e47606f6c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753306"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a>タイム ゾーンと定期的なアイテムが BizTalk Server でスケジュールを構成します。
タイム ゾーンを設定しで、繰り返しのスケジュールを構成、受信場所で[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、受信場所の高度なスケジューリング機能をいくつかのオプションが含まれています。 詳細設定オプションをスケジュールするには、タイム ゾーンを設定およびも、繰り返しのスケジュールを設定を使用します。

このトピックでは、これらの機能を構成する方法を示します。

## <a name="prerequisites"></a>前提条件
インストール[Feature Pack 2](https://aka.ms/bts2016fp2)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。

## <a name="time-zone"></a>タイム ゾーン

**スケジュール**受信場所のプロパティが含まれています、**タイム ゾーン**プロパティ。 設定すると、ローカル コンピューターのタイム ゾーンではなく、受信場所で選択したタイム ゾーンが使用されます。 

すべての日付と時刻で、**スケジュール**プロパティは選択したタイム ゾーンに固有です。 既存のスケジュールは、BizTalk 管理データベース (BizTalkMgmtDb) をホストするサーバーのタイム ゾーンに移行されます。 

夏時間 (DST) を調整することもできます。 選択した場合、スケジュールを選択するタイム ゾーンの夏時間へ自動的に調整します。 このオプションは影響しません、スケジュールの場合。

* 指定されたタイム ゾーンには、夏時間の期間はありません。
* 選択したタイム ゾーンの夏時間のタイムは発生しません

## <a name="enable-recurrence-schedule"></a>定期的なスケジュールを有効にします。
1. **BizTalk Server 管理**コンソールのいずれかを右クリックし、受信場所、および選択**プロパティ**します。 
2. **スケジュール**] ページで、[**有効にするサービス時間帯**します。 **開始時刻**と**停止時刻**スケジュールの実行が許可される最初の時間を設定します。

    ![有効にするサービスの Windows の受信ポート](../core/media/enable-service-windows-for-receive-port.PNG)

3. 追加のスケジュール オプションが表示されます。

    ![高度なスケジュールの受信ポート](../core/media/advanced-scheduling-for-receive-port.PNG)

4. **繰り返し**プロパティは、すべての日、週、または選択した月の受信ポートを実行します。 

    1. 使用、**毎日**受信ポートを実行するには、定期的なアイテムすべて*x*の開始日の数、**から**選択した日付と内でのみ、**サービス ウィンドウ**を選択します。

        ![毎日のスケジュール](../core/media/daily-schedule.png)

    2. 使用して、**毎週**と内でのみ、1 週間以内の特定の日に受信ポートを実行するには、定期的なアイテム、**サービス時間帯**選択します。 

        ![週単位のスケジュール](../core/media/weekly-schedule.png)

    3. 使用して、**毎月**受信ポートを月単位のスケジュールで実行するには、定期的なアイテム。 **日**と**で**オプションを使用できます。 
    
        使用して、**日**内で特定の日付で受信ポートを実行するには、定期的なアイテム、**か月間**選択します。 

        ![月単位のスケジュール](../core/media/monthly-schedule.PNG)

        使用して、**で**月の特定の日に受信ポートを実行するには、定期的なアイテム。

        ![スケジュールで毎月](../core/media/monthly-on-schedule.PNG)

5. **[OK]** を選択して変更を保存します。 

## <a name="see-also"></a>関連項目
[Feature Pack を構成します。](../core/configure-the-feature-pack.md)

---
title: 検証の構成 (X12 インターチェンジの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdad7016-1d66-4d11-b620-c28368f00133
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0782546e8d016aba2f8ccc4bcd5b7ad5e81412de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355092"
---
# <a name="configuring-validation-x12-interchange-settings"></a>検証の構成 (X12 インターチェンジの設定)
X12 インターチェンジの検証生成の設定を定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信したインターチェンジの重複した制御番号を確認します。  
  
> [!NOTE]
>  ここで説明した設定は、HIPAA インターチェンジの検証にも適用されます。  
  
> [!IMPORTANT]
>  プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-validation"></a>検証を構成するには  
  
1. X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2. 一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**検証**です。  
  
3. 選択、**インターチェンジ制御番号**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックス。 選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号 (ISA13) では、インターチェンジ制御番号が一致しないことを確認します。 一致が検出されると、受信パイプラインはインターチェンジを処理できません。  
  
4. 場合**インターチェンジ制御番号**がオン、**内で重複している isa13 を確認**フィールドに、特定を使用して、重複するインターチェンジに対する確認を実行する日数を入力します。インターチェンジ制御番号。  
  
5. 選択**グループ制御番号**受信パイプラインが重複するグループ制御番号 (GS6) のインターチェンジを処理するを防ぐためにします。  
  
6. 選択**トランザクション セット制御番号**受信パイプラインが重複するトランザクション セット制御番号 (ST2) のインターチェンジを処理するを防ぐためにします。  
  
7. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (X12)](../core/configuring-interchange-settings-x12.md)
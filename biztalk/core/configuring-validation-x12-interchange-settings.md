---
title: 検証 (X12 インターチェンジの設定) の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 0edfe66791fa5c041c66a3adddde61730afe54ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233274"
---
# <a name="configuring-validation-x12-interchange-settings"></a>検証の構成 (X12 インターチェンジの設定)
X12 インターチェンジの検証生成設定では、受信したインターチェンジの重複する制御番号を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で確認する方法を定義します。  
  
> [!NOTE]
>  ここで説明する設定は、HIPAA インターチェンジの検証にも適用されます。  
  
> [!IMPORTANT]
>  プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-validation"></a>検証を構成するには  
  
1.  X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**検証**です。  
  
3.  選択、**インターチェンジ制御番号**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックスです。 選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号 (ISA13) が、インターチェンジ制御番号と一致しませんを確認します。 一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。  
  
4.  場合**インターチェンジ制御番号**がオンにした場合、**内で重複している isa13 を確認して**フィールドに、重複するインターチェンジに対する確認は、固有の仕様を使用して実行される日数を入力インターチェンジ制御番号です。  
  
5.  選択**グループ制御番号**を受信パイプラインが重複するグループ制御番号 (GS6) のインターチェンジを処理するを防ぐためにします。  
  
6.  選択**トランザクション セット制御番号**を受信パイプラインが重複しているトランザクション セット制御番号 (ST2) のインターチェンジを処理するを防ぐためにします。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [(X12) インターチェンジの設定を構成します。](../core/configuring-interchange-settings-x12.md)
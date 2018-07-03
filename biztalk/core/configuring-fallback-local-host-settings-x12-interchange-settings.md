---
title: フォールバック ローカル ホスト設定 (X12 インターチェンジの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b552fa2b-1154-491f-9bcf-aaba3b8f343f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57763ad613025f475ae141a884bd9994a8e8a209
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012563"
---
# <a name="configuring-fallback-local-host-settings-x12-interchange-settings"></a>フォールバック ローカル ホスト設定の構成 (X12 インターチェンジの設定)
ローカル ホスト設定は、EDI インターチェンジの処理方法を管理します。 このページの設定は、2 つのカテゴリに分類できます。受信元の設定 (着信インターチェンジ) と送信者の設定 (送信インターチェンジ) です。 受信側の設定の一部として、ST02 (受信確認制御番号) の生成方法を指定できます。 送信者の設定の一部として、送信メッセージの制御番号の生成方法を指定できます。  
  
> [!NOTE]
>  ここで説明する設定は、HIPAA インターチェンジにも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-local-host--receivers-settings"></a>ローカル ホストの受信元の設定を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**ローカル ホストの設定**.  
  
3. 受信確認で使用されるトランザクション セット制御番号の範囲を指定するには、値を入力します。、**確認制御番号 (ST02)** フィールド。 中央の 2 つのフィールドに数値を入力し、プレフィックスとサフィックスのフィールド (省略可能) に英数字を入力します。 中央のフィールドは必須で、制御番号の最小値と最大値を指定します。プレフィックスとサフィックスは省略可能です。 3 つのすべてのフィールドの最大長は 9 文字です。  
  
    最小値にトランザクション セット制御番号を現在のリセット をクリックして**リセット**します。 確認**範囲外の時は下限にリセット**を最大値を超過した後に下限に制御番号をリセットします。  
  
### <a name="to-configure-local-host--senders-settings"></a>ローカル ホストの送信者の設定を構成するには  
  
1.  **インターチェンジ制御番号 (ISA13)**、BizTalk Server で送信インターチェンジの生成で使用するインターチェンジ制御番号の値の範囲を入力します。 1 ～ 999999999 文字の数値を入力します。 これは必須フィールドです。  
  
     制御番号を指定した最小値をリセットする をクリックして、**リセット**ボタンをクリックします。 確認**範囲外の時は下限にリセット**最大値を超えた場合、最小値に自動的にリセットします。  
  
2.  **グループ制御番号 (GS06)**、BizTalk Server グループ制御番号が使用する番号の範囲を入力します。 1 ～ 9 文字の数値を入力します。 このフィールドは必須です。  
  
     グループ制御番号を指定した最小値をリセットする をクリックして、**リセット**ボタンをクリックします。 確認**範囲外の時は下限にリセット**最大値を超えた場合、最小値に自動的にリセットします。  
  
3.  **トランザクション セット制御番号 (ST02)**、 をクリックして**新しい ID を適用**、省略可能なプレフィックスとサフィックスの中央の必須フィールドの数値を指定し、英数字の値の範囲を入力します。 4 つのすべてのフィールドの最大長は 9 文字です。  
  
     最小値にトランザクション セット制御番号を現在のリセット をクリックして**リセット**します。 選択**範囲外の時は下限にリセット**最大値を超過した場合、最小値に制御番号をリセットします。  
  
4.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)
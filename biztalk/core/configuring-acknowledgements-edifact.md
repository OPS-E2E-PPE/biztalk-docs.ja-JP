---
title: 受信確認 (EDIFACT) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269acfa79808f133f4332371d98e491fc8a0b2e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991371"
---
# <a name="configuring-acknowledgements-edifact"></a>受信確認の構成 (EDIFACT)
パートナー アグリーメントでは、どのタイプの確認をパーティに返すかや、どの種類の送信ポートを確認の送信に使用するかを指定できます。 また、確認をバッチ処理するかどうか、どのトランザクション セット参照番号を確認の開始番号にするか、受理されたトランザクション セットに対して SG1/SG4 ループを生成するかどうかも指定します。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
> - **SG1/SG4 ループ受理されたトランザクション セットを生成する (オフの場合、ループが生成されます UCM.5 が 7 と等しくない場合にのみ)** します。  
> 
>   プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a>EDIFACT 確認 (CONTRL) プロパティを構成するには  
  
1.  EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**受信確認**します。  
  
3.  **EDIFACT ACK (制御) セクション**次の操作を行います。  
  
    1.  選択**メッセージの受信 (CONTRL が必要です)** をインターチェンジの送信者に技術確認 (CONTRL) を返します。 場合**メッセージの受信 (CONTRL が必要です)** がオンになっている**メッセージ (CONTRL) メッセージの受信確認をバッチ処理しない**を各受信確認を別々 に送信または受信確認をバッチ処理をオフのままにします。  
  
    2.  選択**確認 (CONTRL) が必要です**をインターチェンジの送信者に機能確認 (CONTRL) を返します。 場合**確認 (CONTRL) が必要です**がオンになっている**確認 (CONTRL) をバッチ処理しない**とは別に、各機能確認を送信またはバッチ機能をオフのままにするには受信確認。  
  
4.  **トランザクション セットの状態への同意レポート**セクションで、機能 CONTRL 確認、受理されたトランザクション セットの SG1/SG4 のループの生成を強制する選択**SG1/SG4 の生成が受け入れられるをループ処理トランザクション セット (オフの場合、ループが生成されます UCM.5 が 7 と等しくない場合にのみ)** します。 SG1/SG4 のループの詳細については、[機能確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-functional-acknowledgment.md)を参照してください。  
  
5.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)
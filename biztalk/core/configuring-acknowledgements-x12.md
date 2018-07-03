---
title: (X12) 受信確認の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28df03b8955c17888a4722c361a2e4481c63b413
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970699"
---
# <a name="configuring-acknowledgements-x12"></a>受信確認の構成 (X12)
パートナー アグリーメントで、パートナーから受信した X12 エンコード インターチェンジへの応答として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で確認を生成する方法、およびパーティーに返す確認の種類を指定できます。 また、確認をバッチ処理するかどうかと、受理されたトランザクション セットに AK2 ループを生成するかどうかを指定できます。 このセクションでは、これらの操作の実行手順について説明します。  
  
> [!NOTE]
>  ここで説明する受信確認プロパティは、HIPAA の受信確認にも適用されます。  
> 
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
> - **受理されたトランザクション セットの AK2 ループを含める (オフの場合、ループが生成されます AK501 が A と等しくない場合にのみ)** します。  
> 
>   プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-x12-ack-properties"></a>X12 確認のプロパティを構成するには  
  
1.  X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、[**インターチェンジの設定**、] をクリックして**受信確認**します。  
  
3.  選択**TA1 が必要**をインターチェンジの送信者に技術 (TA1) 確認を返します。 選択した場合、選択**TA1 をバッチ処理しない**とは別に、各技術確認を送信したり、チェック ボックスを技術確認をバッチ処理をオフのままにします。  
  
4.  選択**997 が必要**機能 (997) 確認をインターチェンジの送信者に戻ります。 選択した場合、選択**997 をバッチ処理しない**とは別に、各機能確認を送信したり、チェック ボックスを機能確認をバッチ処理をオフのままにします。  
  
5.  受理されたトランザクション セットの 997 確認で AK2 ループの生成を有効にするのには、選択**受理されたトランザクション セットに含める AK2 ループ (オフの場合、ループが生成されます AK501 が A と等しくない場合にのみ)** します。 AK2 ループの詳細については、次を参照してください。 [X12 997 受信確認](../core/x12-997-acknowledgment.md)します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (X12)](../core/configuring-interchange-settings-x12.md)
---
title: "エンベロープの構成 (EDIFACT インターチェンジの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531b559e690fae5369298a90cd372edcae79db57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a>エンベロープを構成する (EDIFACT インターチェンジの設定)
このセクションでは、送信 EDIFACT メッセージのエンベロープを構成する方法について説明します。  
  
> [!IMPORTANT]
>  オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-interchange-envelope"></a>インターチェンジ エンベロープを構成するには  
  
1.  EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**エンベロープ**です。  
  
3.  **処理優先度コード (UNB8)**、1 つの文字の最小値と、最大で 1 つの文字でアルファベット順の値を入力します。 このフィールドの入力は省略可能です。  
  
4.  **通信アグリーメント (UNB10)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。 このフィールドは省略可能です。   
  
5.  選択**テスト インジケータ (UNB11)**によって、インターチェンジが生成されることを示すために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト データは、します。  
  
6.  選択**適用の UNA セグメント (文字列サービス通知)**を送信するインターチェンジの UNA セグメントを生成します。 このオプションがオンの場合、 **UNA6**空にすることはできませんと**UNA6 サフィックス**することはできません**None**です。  
  
    > [!NOTE]
    >  指定した**UNA6**と**UNA6 サフィックス**で、**文字セットと区切り記号**ページ」の説明に従って[を構成する文字セットと区切り記号 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).  
  
7.  選択**適用の UNG セグメント (機能グループ ヘッダー)**送信メッセージの機能グループ ヘッダーにグループ化セグメントを作成します。  
  
8.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)
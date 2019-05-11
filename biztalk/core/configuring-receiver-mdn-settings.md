---
title: 受信元 MDN 設定の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c4362ad8acb40bd34f9e0f89751a456ff0fa84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390830"
---
# <a name="configuring-receiver-mdn-settings"></a>受信元 MDN 設定の構成
受信元 MDN 設定の一部として、AS2 メッセージのヘッダーに基づく MDN 生成を制御するプロパティを指定できます。  
  
> [!IMPORTANT]
>  プロパティが無効になりません**パーティ A にパーティ B-> **オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、**パーティ B には、パーティ A が-> ** A を作成するときに、チェック ボックスを選択した場合のタブ  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-receiver-mdn-settings"></a>受信元 MDN 設定を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**受信者の MDN 設定**します。  
  
3.  選択しなかった場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ、**検証** ページで、することもできます、MDN を送信しているパーティがある場合、MDN の署名MDN の生成が有効になって、**ディス ポジション-通知-に**AS2 ヘッダーが、**ディス ポジション-通知オプション**ヘッダーが署名を有効していません。 場合に発生**廃棄通知-オプション**設定されていないか、または省略可能に設定されます。 クリックして行うことができます**廃棄通知-オプションのヘッダーを事前に設定されている場合、または受信プロトコルの署名済みヘッダーが省略可能に設定されている場合要求された MDN に署名**します。  
  
4.  内のテキストを入力することができます、 **MDN テキスト**フィールドに、パーティの送信 MDN が MDN メッセージ (Content-description フィールド) の下に追加します。 この設定は生成かどうか、MDN が AS2 ヘッダーまたはアグリーメント プロパティに基づいてに関係なく適用できます。  
  
5.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)
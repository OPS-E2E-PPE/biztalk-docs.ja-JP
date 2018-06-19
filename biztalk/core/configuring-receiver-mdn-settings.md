---
title: 受信者の MDN 設定の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: dafe17a0ad357b840b31d8a10c67e1ae3cc1e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233378"
---
# <a name="configuring-receiver-mdn-settings"></a>受信者の MDN 設定を構成します。
受信側の MDN 設定の一部として、AS2 メッセージ ヘッダーに基づく MDN 生成を管理するプロパティを指定できます。  
  
> [!IMPORTANT]
>  プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-receiver-mdn-settings"></a>受信側の MDN 設定を構成するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、**受信者の MDN 設定**です。  
  
3.  オンにしなかった場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティに、**検証** ページで、することもできます、MDN を送信しているパーティがある場合、MDN の署名MDN の生成が有効になって、**廃棄で通知を**AS2 ヘッダーが、**廃棄通知オプション**ヘッダーがない署名を有効にします。 これは、場合に発生**廃棄通知オプション**設定されていないか、または省略可能に設定されています。 これを行う をクリックして**廃棄通知オプションのヘッダーがあらかじめ設定されていない場合、または署名 Receipt Protocol ヘッダーが設定されている場合に省略可能な要求された MDN に署名**です。  
  
4.  内のテキストを入力することができます、 **MDN テキスト**フィールドに、MDN メッセージ (Content-description フィールド) の下に追加、MDN を送信しているパーティです。 この設定は、MDN が AS2 ヘッダーまたはアグリーメント プロパティのどちらに基づいて生成されたのかに関係なく、適用できます。  
  
5.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)
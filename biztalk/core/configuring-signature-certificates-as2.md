---
title: 署名証明書 (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa26611b0937385b74773aa4cd9c78477c7e3378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355205"
---
# <a name="configuring-signature-certificates-as2"></a>署名証明書構成 (AS2)
このページの設定の一部として、このアグリーメントに解決されるすべての送信メッセージまたは MDN に署名するために使用する証明書を指定できます。 このページの設定は、BizTalk グループのプロパティの一部として提供される証明書の設定をオーバーライドします。 証明書の使用方法の詳細については、次を参照してください。 [AS2 の証明書を構成](../core/configuring-certificates-for-as2.md)します。  
  
> [!IMPORTANT]
>  プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-agreement-level-signature-certificate"></a>アグリーメント レベルの署名証明書を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、次のようにクリックします。**署名証明書**します。  
  
3.  選択、**上書きグループ署名証明書**送信 AS2 メッセージおよび MDN に署名するため、このページで指定された証明書を使用する チェック ボックス。  
  
4.  クリックして**参照**を表示する、**証明書の選択** ダイアログ ボックスで、このパーティに送信されるメッセージに適用する署名証明書を選択します。  
  
5.  **共通名**テキスト ボックスには、選択した証明書の説明が表示されます。  
  
6.  **拇印**テキスト ボックスは、証明書の拇印を表示します。 証明書の拇印には、形式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数の数字 (0 ~ 9 の数) または a ~ F の文字があります。  
  
7.  クリックして**証明書の削除**を選択した証明書を削除します。  
  
8.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメントのプロパティの構成](../core/configuring-as2-agreement-properties.md)
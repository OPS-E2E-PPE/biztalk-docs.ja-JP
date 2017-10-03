---
title: "(AS2) の署名証明書の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a52962976c2db62de902906f53f5c270e2c7c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-signature-certificates-as2"></a>署名証明書の構成 (AS2)
このページの設定の一部として、このアグリーメントに解決されるすべての送信メッセージまたは MDN の署名に使用される証明書を指定できます。 このページの設定は BizTalk グループのプロパティの一部として提供された証明書設定を上書きします。 証明書の使用方法の詳細については、次を参照してください。 [AS2 用の証明書を構成する](../core/configuring-certificates-for-as2.md)です。  
  
> [!IMPORTANT]
>  プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-agreement-level-signature-certificate"></a>アグリーメントレベルの署名証明書を構成するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブで、をクリックして**署名証明書**です。  
  
3.  選択、**署名証明書の上書きグループ**送信 AS2 メッセージと MDN に署名するため、このページで指定された証明書を使用する チェック ボックスです。  
  
4.  をクリックして**参照**を表示する、**証明書の選択**ダイアログ ボックスで、このパーティから送信されたメッセージに適用する署名証明書を選択します。  
  
5.  **共通名**テキスト ボックスには、選択した証明書の説明が表示されます。  
  
6.  **拇印**テキスト ボックスは、証明書の拇印を表示します。 証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。  
  
7.  をクリックして**証明書の削除**を選択した証明書を削除します。  
  
8.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメント プロパティの構成](../core/configuring-as2-agreement-properties.md)
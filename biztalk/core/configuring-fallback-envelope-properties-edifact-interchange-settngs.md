---
title: フォールバック エンベロープ プロパティ (EDIFACT インターチェンジの設定) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8826041e-02fa-4086-a774-d44a388f42b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a141b852f85947165d3d3d4d638cf1cb10ccb0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22233034"
---
# <a name="configuring-fallback-envelope-properties-edifact-interchange-settngs"></a>フォールバック エンベロープ プロパティの構成 (EDIFACT インターチェンジの設定)
このセクションでは、送信 EDIFACT メッセージのエンベロープを構成する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-interchange-envelope"></a>インターチェンジ エンベロープを構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。  
  
2.  **EDIFACT フォールバックの設定** ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**  タブの 、 **インターチェンジの設定**  をクリックして **エンベロープ**します。  
  
3.  **処理優先度コード (UNB8)**, 、1 文字以上、最大 1 つの文字でアルファベット順の値を入力します。 このフィールドの入力は省略可能です。  
  
4.  **通信アグリーメント (UNB10)**, 、英数字 1 文字以上、35 文字の最大値を入力します。 このフィールドは省略可能です。  
  
5.  選択**テスト インジケータ (UNB11)** によって、インターチェンジが生成されることを示すために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト データは、します。  
  
6.  選択 **適用 UNA セグメント (文字列サービス通知)** を送信するインターチェンジの UNA セグメントを生成します。 このオプションがオンの場合、 **UNA6** 空にすることはできませんと **UNA6 サフィックス** することはできません **None**します。  
  
    > [!NOTE]
    >  指定した**UNA6**と**UNA6 サフィックス**で、**文字セットと区切り記号**ページ」の説明に従って[構成フォールバック文字セットと区切り記号のプロパティ (EDIFACT)](../core/configuring-fallback-charset-and-separator-properties-edifact.md)です。  
  
7.  選択 **適用 UNG セグメント (機能グループ ヘッダー)** 送信メッセージの機能グループ ヘッダーにグループ化セグメントを作成します。  
  
8.  をクリックして **適用** 構成を続行する前にその変更を受け入れるか、クリックして **OK** 、変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)
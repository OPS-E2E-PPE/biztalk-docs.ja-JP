---
title: "フォールバック エンベロープ プロパティの構成 (EDIFACT トランザクション セットの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93f9aae6d67e5dc56d383626e36d1db412be9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a>フォールバック エンベロープ プロパティの構成 (EDIFACT トランザクション セットの設定)
**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する EDIFACT エンコード インターチェンジの UNG セグメントを生成する方法を定義します。  
  
 UNG セグメントは、EDIFACT エンコード インターチェンジの機能グループを識別および指定するヘッダーです。 UNG セグメントには、機能グループに含まれているドキュメントの種類とバージョンのほか、機能グループが準備された日時に関する情報が含まれています。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-define-the-ung-segments"></a>UNG セグメントを定義するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。  
  
2.  **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**エンベロープ**.  
  
3.  **機能グループ ID (UNG1)**、1 つの文字の最小値、最大 6 文字の英数字を入力します。 このフィールドは必須です。  
  
4.  識別する値を入力**アプリケーション送信者 (UNG2)**です。  
  
    -   **Id (UNG2.1)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。 このフィールドは必須です。  
  
    -   **コードの修飾子 (UNG2.2)**、1 つの文字の最小値、最大 4 文字の英数字を入力します。 このフィールドの入力は省略可能です。  
  
5.  識別する値を入力**アプリケーション受信者 (UNG3)**です。  
  
    -   **の Id (UNG3.1)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。 このフィールドは必須です。  
  
    -   **コードの修飾子 (UNG3.2)**、1 つの文字の最小値、最大 4 文字の英数字を入力します。 このフィールドの入力は省略可能です。  
  
6.  **制御機関 (UNG6)**、1 つの文字の最小値、最大 2 つの文字の英数字を入力します。 このフィールドは必須です。  
  
7.  識別する値を入力**メッセージ バージョン (UNG7)**です。  
  
    -   **バージョン (UNG7.1)**、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。 このフィールドは必須です。  
  
    -   **リリース (UNG7.2)**、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。 このフィールドは必須です。  
  
    -   **関連付けの割り当てコード (UNG7.3)**、1 文字の最小値、最大 6 文字の英数字を入力します。 このフィールドの入力は省略可能です。  
  
8.  **アプリケーション パスワード (UNG8)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。 このフィールドは必須です。  
  
9. をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクションの EDIFACT フォールバック アグリーメント プロパティの構成設定](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)
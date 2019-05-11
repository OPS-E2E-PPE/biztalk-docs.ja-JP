---
title: フォールバック エンベロープ プロパティの構成 (EDIFACT トランザクション セットの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0dbad19076ab457f91dc41970d1c07c88cf45e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391332"
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a>フォールバック エンベロープ プロパティの構成 (EDIFACT トランザクション セットの設定)
**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する EDIFACT エンコード インターチェンジの UNG セグメントを生成する方法を定義します。  
  
 UNG セグメントは、ヘッダーを識別し、EDIFACT エンコード インターチェンジの機能グループを指定します。 種類と、機能グループ内のドキュメントのバージョンと共に、機能グループが準備された日時に関する情報が含まれています。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-define-the-ung-segments"></a>UNG セグメントを定義するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。  
  
2. **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**封筒**.  
  
3. **機能グループ ID (UNG1)**、1 つの文字の最小値、最大 6 文字の英数字を入力します。 このフィールドは必須です。  
  
4. 識別する値を入力して**アプリケーション送信者 (UNG2)** します。  
  
   -   **Id (UNG2.1)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。 このフィールドは必須です。  
  
   -   **コードの修飾子 (UNG2.2)**、1 つの文字の最小値、最大 4 文字の英数字を入力します。 これは、オプションのフィールドです。  
  
5. 識別する値を入力して**アプリケーション受信者 (UNG3)** します。  
  
   -   **の Id (UNG3.1)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。 このフィールドは必須です。  
  
   -   **コードの修飾子 (UNG3.2)**、1 つの文字の最小値、最大 4 文字の英数字を入力します。 これは、オプションのフィールドです。  
  
6. **制御機関 (UNG6)**、1 つの文字の最小値、最大 2 つの文字の英数字を入力します。 このフィールドは必須です。  
  
7. 識別する値を入力して**メッセージ バージョン (UNG7)** します。  
  
   -   **バージョン (UNG7.1)**、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。 このフィールドは必須です。  
  
   -   **リリース (UNG7.2)**、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。 このフィールドは必須です。  
  
   -   **関連付けの割り当てコード (UNG7.3)**、1 文字の最小値、最大 6 文字の英数字を入力します。 これは、オプションのフィールドです。  
  
8. **アプリケーション パスワード (UNG8)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。 このフィールドは必須です。  
  
9. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セット設定の EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)
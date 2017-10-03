---
title: "フォールバック エンベロープ プロパティ (X12 トランザクション セットの設定) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa7898d1e1a83da879400a89d5cd089ef2d4069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a>フォールバック エンベロープ プロパティの構成 (X12 トランザクション セットの設定)
**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する X12 エンコード インターチェンジの GS セグメントを生成する方法を定義します。 GS セグメントは、X12 エンコード インターチェンジの機能グループを識別および指定します。  
  
> [!NOTE]
>  このトピックは、HIPAA 関連の設定にも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-define-the-gs-segments"></a>GS セグメントを定義するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。  
  
2.  **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**エンベロープ**.  
  
3.  **機能コード (GS01)**、ドロップダウン リストから値を選択します。  
  
4.  **アプリケーション送信者 (GS02)**2 の最小値、15 文字の英数字を入力します。 このフィールドは必須です。  
  
5.  **アプリケーション受信者 (GS03)**2 の最小値、15 文字の英数字を入力します。 このフィールドは必須です。  
  
6.  **日付形式 (GS04)**、CCYYMMDD または YYMMDD をドロップダウン リストから選択します。 このフィールドは必須です。  
  
7.  **時刻の形式 (GS05)**HHMM、HHMMSS、または HHMMSSdd をドロップダウン リストから選択します。 このフィールドは必須です。  
  
8.  **担当機関 (GS07)**、ドロップダウン リストから値を選択します。  
  
9. **ドキュメント識別子 (GS08)**、最小値は 1、12 文字の英数字を入力します。 このフィールドの入力は省略可能です。  
  
10. をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [設定の X12 フォールバック アグリーメントのプロパティをトランザクション セットの設定](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)
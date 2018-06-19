---
title: フォールバック検証プロパティ (X12) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a64431d-373a-4d63-9b83-cbb323620152
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6eb44f2ee4c2f9c63011dc14be41380c245996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233154"
---
# <a name="configuring-fallback-validation-properties-x12"></a>フォールバック検証プロパティの構成 (X12)
X12 インターチェンジの検証生成のフォールバック設定は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信したインターチェンジ内の重複した制御番号の有無を確認する方法を定義します。  
  
> [!NOTE]
>  ここで説明する設定は、HIPAA インターチェンジの検証にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-validation"></a>検証を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。  
  
2.  **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**検証**.  
  
3.  選択、**インターチェンジ制御番号**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックスです。 選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号 (ISA13) が、インターチェンジ制御番号と一致しませんを確認します。 一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。  
  
4.  場合**インターチェンジ制御番号**がオンにした場合、**内で重複している isa13 を確認して**フィールドに、重複するインターチェンジに対する確認は、固有の仕様を使用して実行される日数を入力インターチェンジ制御番号です。  
  
5.  選択**グループ制御番号**を受信パイプラインが重複するグループ制御番号 (GS6) のインターチェンジを処理するを防ぐためにします。  
  
6.  選択**トランザクション セット制御番号**を受信パイプラインが重複しているトランザクション セット制御番号 (ST2) のインターチェンジを処理するを防ぐためにします。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)
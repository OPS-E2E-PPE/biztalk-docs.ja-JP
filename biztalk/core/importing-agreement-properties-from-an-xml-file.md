---
title: "アグリーメントのプロパティを XML ファイルからインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3ac08628931ec4111eb1b5a9ad86991344c22d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-agreement-properties-from-an-xml-file"></a>XML ファイルからのアグリーメント プロパティのインポート
ここでは、XML テンプレート ファイルからアグリーメントのプロパティをインポートする方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件を次に示します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
-   必要がありますがエクスポートしたアグリーメントを XML テンプレート ファイル」の説明に従って[アグリーメントのプロパティを XML ファイルにエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)です。  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a>アグリーメントのプロパティを XML ファイルからインポートするには  
  
1.  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理コンソールで、をクリックして、**パーティ**ノードの下、 **BizTalk Server 管理コンソール**と**BizTalk グループ**ノード。 **パーティとビジネス プロファイル** ページで、アグリーメントを作成する」の説明に従って[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。  
  
2.  **アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして**テンプレートからロード**です。  
  
    > [!NOTE]
    >  **テンプレートからロード**アグリーメントのプロトコルを選択した後のみ、ボタンが有効にします。 プロトコルを指定するときは、その同じエンコード プロトコルを使用した場合にのみアグリーメントをインポートできることを明示的に宣言することにもなります。  
  
3.  **開く**ダイアログ ボックスで、XML テンプレート ファイルの場所を参照、ファイルを選択してをクリックして**開く**です。  
  
4.  **テンプレートの作成**ボックスで、クリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [別のアグリーメント プロパティの再利用](../core/reusing-properties-from-another-agreement.md)   
 [アグリーメントのプロパティを XML ファイルにエクスポートします。](../core/exporting-agreement-properties-to-an-xml-file.md)
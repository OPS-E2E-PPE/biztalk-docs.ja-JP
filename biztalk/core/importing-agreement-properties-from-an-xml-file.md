---
title: アグリーメントのプロパティを XML ファイルからインポートする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b8189ce340cb541ab0535f40312f9deec90796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382565"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a>アグリーメントのプロパティを XML ファイルからインポートします。
このセクションでは、アグリーメントのプロパティを XML テンプレート ファイルからインポートする方法を説明します。  
  
## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
- 必要がありますをエクスポートしたアグリーメントを XML テンプレート ファイル」の説明に従って[アグリーメントのプロパティを XML ファイルにエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)します。  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a>アグリーメントのプロパティを XML ファイルからインポートするには  
  
1.  BizTalk Server 管理コンソールで、をクリックして、**パーティ**ノードの下、 **BizTalk Server 管理**と**BizTalk グループ**ノード。 **パーティとビジネス プロファイル** ページで、契約の作成」の説明に従って[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。  
  
2.  **アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして**テンプレートからロード**します。  
  
    > [!NOTE]
    >  **テンプレートからロード**アグリーメントのプロトコルを選択した後のみにボタンが有効になります。 プロトコルを指定するときにも暗黙的に宣言する同じエンコード プロトコル用の契約をインポートすることのみできます。  
  
3.  **オープン**XML テンプレート ファイルの場所を参照、ファイルを選択、および順にクリックします ダイアログ ボックスで、**オープン**。  
  
4.  **テンプレートの作成**ボックスで、 **OK**します。  
  
## <a name="see-also"></a>参照  
 [別のアグリーメント プロパティの再利用](../core/reusing-properties-from-another-agreement.md)   
 [XML ファイルへのアグリーメント プロパティのエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)
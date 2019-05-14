---
title: アダプター メタデータを BizTalk プロジェクトに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f06b60b1dce1b0b9df785d25552f688f7793858
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387309"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a>アダプター メタデータを BizTalk プロジェクトに追加する方法
アダプター メタデータの追加ウィザードでは、アダプター メタデータを BizTalk プロジェクトに追加することができます。 このデータには、スキーマ、メッセージの種類、およびオーケストレーションからアダプターと通信するために必要なポートの種類が含まれます。 アダプター メタデータの追加ウィザードを使用して、FTP などのアプリケーション アダプター、システムにこれらのアプリケーション アダプターに対応するプル スキーマを使用します。 HTTP などのトランスポート アダプターによってスキーマは通常使用しないように注意してください。  
  
 次の手順では、アダプターのメタデータを追加する汎用的な手順について説明します。  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a>アダプター メタデータを BizTalk プロジェクトに追加するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**生成した項目の追加**します。  
  
2. **生成した項目の追加 - \<** <em>プロジェクト名</em>**\>**  ダイアログ ボックスで、**テンプレート** セクションで、選択**アダプターの追加**、 をクリックし、**オープン**。  
  
3. アダプター メタデータの追加ウィザードで、**アダプターの選択**ページで、次の操作を行います。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |アダプターのリスト ボックス|プロジェクトに追加する登録済みのアダプターを選択します。|  
   |SQL Server|BizTalk データベース サーバー名を入力します。|  
   |[データベース]|選択したサーバーの BizTalk 管理データベースの一覧が表示されます。|  
   |Port|任意。 作成され、BizTalk 管理データベースに格納されているポートの一覧が表示されます。 選択したアダプターを使用するように構成ポートのみ表示されます。|  
  
    **[次へ]** をクリックします。  
  
   > [!NOTE]
   >  文字が含まれている生成されたスキーマを追加しようとすると、 **System.XML.XMLConvert**クラスでは、コンパイル エラーの結果をサポートしません。  
  
4. 静的アダプターを使用している場合、 **[インポートするサービス**] ページで、ツリー ビューから利用可能なサービスのセットを選択してクリックして**完了**します。  
  
    または、  
  
    動的アダプターを使用している場合は、ウィザードを完了するカスタム ユーザー インターフェイスの手順に従います。  
  
   ウィザードを完了した後[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで .odx および .xsd ファイルを示します。
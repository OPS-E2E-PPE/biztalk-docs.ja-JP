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
ms.openlocfilehash: 0c95cfac206dad58e0093945d2495c7e725c849c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968809"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a>アダプター メタデータを BizTalk プロジェクトに追加する方法
アダプター メタデータの追加ウィザードを使用すると、アダプター メタデータを BizTalk プロジェクトに追加できます。 このデータには、オーケストレーションからアダプターと通信するために必要なスキーマ、メッセージの種類、およびポートの種類が含まれます。 FTP などのアプリケーション アダプターと共にアダプター メタデータの追加ウィザードを使用することで、これらのアプリケーション アダプターに対応するスキーマをシステムに取り込むことができます。 HTTP などのトランスポート アダプターでは通常、スキーマが使用されません。  
  
 次の手順は、アダプターのメタデータを追加する一般的な手順です。  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a>BizTalk プロジェクトにアダプター メタデータを追加するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、] をクリックし、**生成した項目の追加**します。  
  
2. **生成した項目の追加 - \<** <em>プロジェクト名</em>**\>**  ダイアログ ボックスで、**テンプレート** セクションで、選択**アダプターの追加**、 をクリックし、**オープン**。  
  
3. アダプター メタデータの追加ウィザードで、**アダプターの選択**ページで、次の操作を行います。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |[アダプター] ボックス|プロジェクトに追加する登録済みのアダプターを選択します。|  
   |SQL Server|BizTalk データベース サーバーの名前を入力します。|  
   |[データベース]|選択したサーバーの BizTalk 管理データベースの一覧が表示されます。|  
   |Port|任意。 作成されて、BizTalk 管理データベースに格納されているポートの一覧を表示します。 選択したアダプターで使用できるように構成されているポートだけが表示されます。|  
  
    **[次へ]** をクリックします。  
  
   > [!NOTE]
   >  文字が含まれている生成されたスキーマを追加しようとすると、 **System.XML.XMLConvert**クラスでは、コンパイル エラーの結果をサポートしません。  
  
4. 静的アダプターを使用している場合、 **[インポートするサービス**] ページで、ツリー ビューから利用可能なサービスのセットを選択してクリックして**完了**します。  
  
    または、  
  
    動的アダプターを使用している場合は、カスタム ユーザー インターフェイスの手順に従ってウィザードを実行します。  
  
   ウィザードが完了すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーに、.odx ファイルおよび .xsd ファイルが表示されます。
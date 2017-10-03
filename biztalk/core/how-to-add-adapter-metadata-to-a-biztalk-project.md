---
title: "アダプター メタデータを BizTalk プロジェクトに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b343ff085cee7049ea916a38fe1216e097200fbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a>アダプター メタデータを BizTalk プロジェクトに追加する方法
アダプター メタデータの追加ウィザードを使用すると、アダプター メタデータを BizTalk プロジェクトに追加できます。 このデータには、オーケストレーションからアダプターと通信するために必要なスキーマ、メッセージの種類、およびポートの種類が含まれます。 FTP などのアプリケーション アダプターと共にアダプター メタデータの追加ウィザードを使用することで、これらのアプリケーション アダプターに対応するスキーマをシステムに取り込むことができます。 HTTP などのトランスポート アダプターでは通常、スキーマが使用されません。  
  
 次の手順は、アダプターのメタデータを追加する一般的な手順です。  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a>BizTalk プロジェクトにアダプター メタデータを追加するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加 - \<** *プロジェクト名* **>**   ダイアログ ボックスで、**テンプレート** セクションで、選択**アダプターの追加**、クリックして**開く**です。  
  
3.  アダプター メタデータの追加ウィザードで、**アダプターの選択** ページで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[アダプター] ボックス|プロジェクトに追加する登録済みのアダプターを選択します。|  
    |SQL Server|BizTalk データベース サーバーの名前を入力します。|  
    |データベース|選択したサーバーの BizTalk 管理データベースの一覧を表示します。|  
    |ポート|省略可。 作成されて、BizTalk 管理データベースに格納されているポートの一覧を表示します。 選択したアダプターで使用できるように構成されているポートだけが表示されます。|  
  
     **[次へ]**をクリックします。  
  
    > [!NOTE]
    >  文字が含まれている生成されたスキーマを追加しようとすると、 **System.XML.XMLConvert**クラスは、コンパイル エラーの結果をサポートしません。  
  
4.  静的なアダプターを使用している場合、 **[インポートするサービス**] ページで、ツリー ビューから利用可能なサービスのセットを選択してをクリックして**完了**です。  
  
     - または -  
  
     動的アダプターを使用している場合は、カスタム ユーザー インターフェイスの手順に従ってウィザードを実行します。  
  
 ウィザードが完了すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーに、.odx ファイルおよび .xsd ファイルが表示されます。
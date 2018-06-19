---
title: BizTalk プロジェクト システムの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5b8c3a83d75219b9e52fd2ab13124480d772832
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008195"
---
# <a name="using-the-biztalk-project-system"></a>BizTalk プロジェクト システムの使用
BizTalk プロジェクト システムを使用すると、BizTalk ソリューションを Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境で作成、編成、および構成できます。 このセクションの各トピックおよび手順では、BizTalk プロジェクト システムを使用して、さまざまな作業を行う方法について説明しています。  
  
 BizTalk Server プロジェクト システムでは、同じプロジェクト管理の原則と内の他の Microsoft Build Engine (MSBuild) プロジェクトで使用するプロシージャ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。 このセクションでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で動作するアプリケーションの作成で行われる共通の作業手順について説明します。  
  
 MSBuild の詳細については、MSBuild のリファレンス セクションを参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)です。  
  
 使用しての詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境では、「管理ソリューション、プロジェクト、およびファイル」を参照して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx)です。  
  
 次の図は、BizTalk プロジェクト システム設計環境で、**新しいプロジェクト**ダイアログ ボックスが表示されます。  
  
 ![プロジェクト システム](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")  
プロジェクト システム設計環境を示しています。  
  
### <a name="to-open-biztalk-editor"></a>BizTalk エディターを開くには  
  
1.  ソリューション エクスプローラーで、スキーマをクリックします。  
  
    > [!NOTE]
    >  BizTalk エディターを開くには、最初にスキーマを作成するか、既存のスキーマを開く必要があります。 スキーマを作成する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)です。 参照してください[プロジェクト項目の追加](../core/adding-project-items.md)です。  
  
2.  **ビュー**  メニューのをクリックして**開く**です。  
  
     - または -  
  
     スキーマを右クリックし、をクリックして**開く**です。  
  
     - または -  
  
     スキーマをダブルクリックします。  
  
     選択されたスキーマが BizTalk エディターに表示されます。  
  
    > [!NOTE]
    >  スキーマを作成するには、プロジェクトを開く必要があります。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。 プロジェクトに項目を追加する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)です。 参照してください[プロジェクト項目の追加](../core/adding-project-items.md)です。  
  
### <a name="to-open-biztalk-mapper"></a>BizTalk マッパーを開くには  
  
1.  ソリューション エクスプローラーで、マップをクリックします。  
  
    > [!NOTE]
    >  BizTalk マッパーを開くには、最初にマップを作成するか、既存のマップを開く必要があります。 マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)です。 参照してください[プロジェクト項目の追加](../core/adding-project-items.md)です。  
  
2.  **ビュー**  メニューのをクリックして**開く**です。  
  
     - または -  
  
     マップを右クリックし、をクリックして**開く**です。  
  
     - または -  
  
     マップをダブルクリックします。  
  
     選択されたマップが BizTalk マッパーに表示されます。  
  
    > [!NOTE]
    >  マップを作成するには、プロジェクトを開く必要があります。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。 プロジェクトに項目を追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)です。 参照してください[新しいマップを作成する方法](../core/how-to-create-new-maps.md)です。  
  
### <a name="to-open-orchestration-designer"></a>オーケストレーション デザイナーを開くには  
  
1.  ソリューション エクスプローラーで、オーケストレーション (.odx) をクリックします。  
  
    > [!NOTE]
    >  オーケストレーション デザイナーを開くには、最初にオーケストレーションを作成するか、既存のオーケストレーションを開く必要があります。 オーケストレーションを作成する方法については、次を参照してください。[オーケストレーション デザイナーでの作業](../core/working-in-orchestration-designer.md)です。  
  
2.  **ビュー**  メニューのをクリックして**開く**です。  
  
     - または -  
  
     オーケストレーションを右クリックし、をクリックして**開く**です。  
  
     - または -  
  
     オーケストレーションをダブルクリックします。  
  
     オーケストレーション デザイナーが開きます。  
  
    > [!NOTE]
    >  オーケストレーションを作成するには、プロジェクトを開く必要があります。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。 プロジェクトに項目を追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)です。 参照してください[オーケストレーション デザイナーでの作業](../core/working-in-orchestration-designer.md)です。  
  
### <a name="to-open-pipeline-designer"></a>パイプライン デザイナーを開くには  
  
1.  ソリューション エクスプローラーで、パイプラインをクリックします。  
  
    > [!NOTE]
    >  パイプライン デザイナーを開くには、最初にパイプラインを作成するか、既存のパイプラインを開く必要があります。 パイプラインを作成する方法については、次を参照してください。[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)です。  
  
2.  **ビュー**  メニューのをクリックして**開く**です。  
  
     - または -  
  
     パイプラインを右クリックし、をクリックして**開く**です。  
  
     - または -  
  
     パイプラインをダブルクリックします。  
  
     パイプライン デザイナーが表示されます。  
  
    > [!NOTE]
    >  パイプラインを作成するには、プロジェクトを開く必要があります。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。 プロジェクトに項目を追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)です。 参照してください[オーケストレーション デザイナーでの作業](../core/working-in-orchestration-designer.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)   
 [パイプライン デザイナーの使用](../core/using-pipeline-designer.md)   
 [ビジネス ルール作成ツールの Windows](../core/windows-of-the-business-rule-composer.md)   
 [BizTalk エディターの使用](../core/using-biztalk-editor.md)   
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)   
 [開発ツール](../core/developer-tools.md)
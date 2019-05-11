---
title: BizTalk プロジェクト システムの使用 |Microsoft Docs
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
ms.openlocfilehash: 2401048d928a628a4dd4063d6a3e207c78e2155f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320888"
---
# <a name="using-the-biztalk-project-system"></a>BizTalk プロジェクト システムの使用
BizTalk プロジェクト システムを使用して、作成、整理、および microsoft BizTalk ソリューションを構成する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境。 トピックと、このセクションの手順では、BizTalk プロジェクト システムを使用してさまざまなタスクを実行する方法を説明します。  
  
 BizTalk Server プロジェクト システムでは、同じプロジェクト管理の原則と他の Microsoft Build Engine (MSBuild) プロジェクトで使用するプロシージャ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 このセクションでは、Microsoft で実行するアプリケーションを作成するときに使用する一般的な手順をについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 MSBuild の詳細については、MSBuild のリファレンス セクションを参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)します。  
  
 使用しての詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境の「管理ソリューション、プロジェクト、およびファイル」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[ http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx)します。  
  
 BizTalk プロジェクト システム設計環境を次に示します、**新しいプロジェクト**ダイアログ ボックスが表示されます。  
  
 ![プロジェクト システム](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")  
プロジェクト システム設計環境を示しています。  
  
### <a name="to-open-biztalk-editor"></a>BizTalk エディターを開く  
  
1.  ソリューション エクスプ ローラーでスキーマをクリックします。  
  
    > [!NOTE]
    >  BizTalk エディターを開くには、まずスキーマを作成または、以前に作成したスキーマを開く必要があります。 スキーマを作成する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)します。 参照してください[プロジェクト項目の追加](../core/adding-project-items.md)します。  
  
2.  **ビュー**  メニューのをクリックして**オープン**します。  
  
     - または -  
  
     スキーマを右クリックし、をクリックし、**オープン**します。  
  
     - または -  
  
     スキーマをダブルクリックします。  
  
     選択したスキーマが BizTalk エディターで開きます。  
  
    > [!NOTE]
    >  スキーマを作成するには、プロジェクトを開いてが必要です。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。 項目をプロジェクトに追加する方法の詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)します。 参照してください[プロジェクト項目の追加](../core/adding-project-items.md)します。  
  
### <a name="to-open-biztalk-mapper"></a>BizTalk マッパーを開く  
  
1.  ソリューション エクスプ ローラーでマップをクリックします。  
  
    > [!NOTE]
    >  BizTalk マッパーを開くには、まずマップを作成するか、以前に作成したマップを開く必要があります。 マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)します。 参照してください[プロジェクト項目の追加](../core/adding-project-items.md)します。  
  
2.  **ビュー**  メニューのをクリックして**オープン**します。  
  
     - または -  
  
     クリックして、マップを右クリックして**オープン**します。  
  
     - または -  
  
     マップをダブルクリックします。  
  
     選択したマップは、BizTalk マッパーで開きます。  
  
    > [!NOTE]
    >  マップを作成するには、プロジェクトを開いてが必要です。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。 項目をプロジェクトに追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)します。 参照してください[新しいマップを作成する方法](../core/how-to-create-new-maps.md)します。  
  
### <a name="to-open-orchestration-designer"></a>オーケストレーション デザイナーを開く  
  
1.  ソリューション エクスプ ローラーで、オーケストレーション (.odx) をクリックします。  
  
    > [!NOTE]
    >  オーケストレーション デザイナーを開くには、最初にオーケストレーションを作成するか、以前に作成したオーケストレーションを開く必要があります。 オーケストレーションを作成する方法については、次を参照してください。[オーケストレーション デザイナーを使用して](../core/working-in-orchestration-designer.md)します。  
  
2.  **ビュー**  メニューのをクリックして**オープン**します。  
  
     - または -  
  
     クリックして、オーケストレーションを右クリックして**オープン**します。  
  
     - または -  
  
     オーケストレーションをダブルクリックします。  
  
     オーケストレーション デザイナーが開きます。  
  
    > [!NOTE]
    >  オーケストレーションを作成するには、プロジェクトを開いてが必要です。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。 項目をプロジェクトに追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)します。 参照してください[オーケストレーション デザイナーを使用して](../core/working-in-orchestration-designer.md)します。  
  
### <a name="to-open-pipeline-designer"></a>パイプライン デザイナーを開く  
  
1.  ソリューション エクスプ ローラーでは、パイプラインをクリックします。  
  
    > [!NOTE]
    >  パイプライン デザイナーを開くには、最初にパイプラインを作成するか、以前に作成したパイプラインを開く必要があります。 パイプラインを作成する方法については、次を参照してください。[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)します。  
  
2.  **ビュー**  メニューのをクリックして**オープン**します。  
  
     - または -  
  
     パイプラインを右クリックし、をクリックし、**オープン**します。  
  
     - または -  
  
     パイプラインをダブルクリックします。  
  
     パイプライン デザイナーが開きます。  
  
    > [!NOTE]
    >  パイプラインを作成するには、プロジェクトを開いてが必要です。 プロジェクトを作成する方法については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。 項目をプロジェクトに追加する方法の詳細については、次を参照してください。[プロジェクト項目の追加](../core/adding-project-items.md)します。 参照してください[オーケストレーション デザイナーを使用して](../core/working-in-orchestration-designer.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)   
 [パイプライン デザイナーの使用](../core/using-pipeline-designer.md)   
 [ビジネス ルール作成ツールの Windows](../core/windows-of-the-business-rule-composer.md)   
 [BizTalk エディターを使用してください。](../core/using-biztalk-editor.md)   
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)   
 [開発ツール](../core/developer-tools.md)
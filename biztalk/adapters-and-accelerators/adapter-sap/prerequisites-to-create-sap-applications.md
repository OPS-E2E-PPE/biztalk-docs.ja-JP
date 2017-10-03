---
title: "SAP アプリケーションを作成する前提条件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51ae9569-4081-4142-9ee2-8ae0069e9d90
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7cddc252868bf47ace0d73e81ddb1c7721bf8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-sap-applications"></a>SAP アプリケーションを作成するための必要条件
このセクションの内容を使用して BizTalk アプリケーションを開発する前に行う必要がありますタスクに関する情報を提供する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 セクションには、BizTalk アプリケーションの開発に使用される一部の BizTalk Server ツールも表示されます。  
  
## <a name="create-a-strong-name-key-file"></a>厳密な名前キー ファイルを作成します。

Microsoft でプロジェクトをビルドするための厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合)-と公開キーおよびデジタル署名します。 厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。  
  
> [!IMPORTANT]
>  1 回限りのタスクは、厳密な名前キー ファイルを作成します。 すべての BizTalk アプリケーションを開発するため、同じキーを使用できます。  
  
1.  Visual Studio 用開発者コマンド プロンプトを開きます。  
  
2.  コマンド プロンプトで、キー ファイルを作成する場所に移動します。 たとえば、入力**cd C:\Sample**、ENTER キーを押します。  
  
3.  コマンド プロンプトで「`sn -k <key file name\>.snk`」と入力し、Enter キーを押します。  
  
    > [!NOTE]
    >  厳密な名前キー ファイルへのキー ペアが作成されたことを示すコマンド プロンプトでメッセージが表示されます。  
  
4.  コマンド プロンプトで次のように入力します。**終了**、ENTER キーを押します。  

## <a name="learn-the-biztalk-server-tools"></a>BizTalk Server ツールを説明します。

使用する方法に関するトピック、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)BizTalk Server ツールの数に関する実用的な知識があることを前提としています。 使用して BizTalk アプリケーションを開発する、次のツールを使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
-   Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 
  
-   オーケストレーション eesigner  
  
-   パイプライン デザイナー  
  
-   BizTalk マッパー  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管理コンソール  

  
### <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ツールを使用するには、まず [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] をインストールする必要があります。  
  
### <a name="biztalk-server-tools"></a>BizTalk Server ツール  
 次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]各ツールの使用方法を説明するドキュメントです。  

|ツール|トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主要マニュアル|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|-   [Visual Studio の使用](../../core/using-visual-studio.md) <br />-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)<br />-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 詳細についての Visual Studio ソリューション、プロジェクトでは、ある項目の[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)です。|  
|オーケストレーション デザイナー|[オーケストレーション デザイナーを使用してオーケストレーションの作成](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|パイプライン デザイナー| [パイプライン デザイナーを使用してパイプラインを作成します。](../../core/creating-pipelines-using-pipeline-designer.md)|  
|BizTalk マッパー| [BizTalk マッパーを使用してマップを作成します。](../../core/creating-maps-using-biztalk-mapper.md)|  
|BizTalk Server 管理コンソール|[BizTalk Server 管理コンソールの使用](../../core/using-the-biztalk-server-administration-console.md)|  

## <a name="next"></a>Next
[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
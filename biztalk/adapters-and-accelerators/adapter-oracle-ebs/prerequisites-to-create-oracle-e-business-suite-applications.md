---
title: Oracle E-business Suite アプリケーションを作成する前提条件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b02ea286-f301-46b3-b748-d954dead23a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90eac318264f53e95aade98cf9574fc0eea45483
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216762"
---
# <a name="prerequisites-to-create-oracle-e-business-suite-applications"></a>Oracle E-business Suite アプリケーションを作成するための必要条件
このセクションの内容を使用して BizTalk アプリケーションを開発する前に行う必要がありますに関する情報を提供する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 このセクションのリンクもに、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk アプリケーションを開発するために使用するツールです。  
  
## <a name="create-a-strong-named-key-file"></a>厳密な名前キー ファイルを作成します。

Microsoft でプロジェクトをビルドするための厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合)-と公開キーおよびデジタル署名します。 厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。  
  
> [!IMPORTANT]
>  1 回限りのタスクは、厳密な名前キー ファイルを作成します。 すべての BizTalk アプリケーションを開発するため、同じキーを使用できます。  
  
### <a name="prerequisites"></a>前提条件  
 Microsoft に設定する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]厳密な名前キーを作成するコンピューターにインストールします。  
  
### <a name="create-a-strong-name-key-file"></a>厳密な名前キー ファイルを作成します。  
  
1.  Visual Studio 用開発者コマンド プロンプトを開きます。  
  
2.  コマンド プロンプトで、キー ファイルを作成する場所に移動します。 たとえば、「 `cd C:\Sample`、ENTER キーを押します。  
  
3.  コマンド プロンプトで「`sn -k <key file name>.snk`」と入力し、Enter キーを押します。  
  
    > [!NOTE]
    >  厳密な名前キー ファイルへのキー ペアが作成されたことを示すコマンド プロンプトでメッセージが表示されます。  
  
4.  コマンド プロンプトで「`exit`」と入力し、Enter キーを押します。  
  
## <a name="learn-the-biztalk-server-tools"></a>BizTalk Server ツールを説明します。

使用する方法に関するトピック、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)の数に関する実用的な知識があることを想定して記述された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールです。 使用して BizTalk アプリケーションを開発する、次のツールを使用するが、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
-   Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 
  
-   BizTalk エクスプローラー  
  
-   オーケストレーション eesigner  
  
-   パイプライン デザイナー  
  
-   BizTalk マッパー  
  
-   BizTalk Server 管理コンソール  
  
### <a name="prerequisites"></a>前提条件  
 Microsoft をインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]にアクセスできるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールです。  
  
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

[Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)  
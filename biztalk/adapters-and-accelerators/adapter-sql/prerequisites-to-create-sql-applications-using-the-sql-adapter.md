---
title: SQL アダプターを使用して SQL アプリケーションを作成する前提条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb3a8963-88a8-4db0-a740-eb54b041931c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b9cf36e67a8146161faa6805153e9c2eed7990a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368475"
---
# <a name="prerequisites-to-create-sql-applications-using-the-sql-adapter"></a>SQL アダプターを使用して SQL アプリケーションを作成するための必要条件
使用して BizTalk アプリケーションを開発する前に行う必要があります、[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]します。 トピックには、BizTalk アプリケーションの開発に使用されるいくつかの BizTalk Server ツールも一覧表示されます。  

## <a name="create-a-strong-named-key-file"></a>厳密な名前キー ファイルを作成します。
Microsoft でプロジェクトをビルドする厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合) と公開キーおよびデジタル署名。 厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。  

> [!IMPORTANT]
>  1 回限りのタスクは、厳密な名前キー ファイルを作成します。 同じキーは、開発したすべての BizTalk アプリケーションを使用することができます。  

### <a name="prerequisites"></a>前提条件  
 Microsoft が必要[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]厳密な名前キーを作成するコンピューターにインストールします。  

### <a name="create-a-strong-name-key-file"></a>厳密な名前キー ファイルを作成します。  

1.  Visual Studio 用開発者コマンド プロンプトを開きます。  

2.  コマンド プロンプトでは、キー ファイルを作成する場所に移動します。 たとえば、「 `cd C:\Sample`、し、ENTER キーを押します。  

3.  コマンド プロンプトで「`sn -k <key file name>.snk`」と入力し、Enter キーを押します。  

    > [!NOTE]
    >  キーのペアが厳密な名前キー ファイルに書き込まれたことを示すコマンド プロンプトでのメッセージが表示されます。  

4.  コマンド プロンプトで「`exit`」と入力し、Enter キーを押します。  

## <a name="learn-the-biztalk-server-tools"></a>BizTalk Server ツールについて説明します

使用する方法に関するトピック、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)の数に関する実用的な知識があることを前提として記述された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。 次のツールを使用して BizTalk アプリケーションの開発を使用して、 [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:  

- Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 

- BizTalk エクスプ ローラー  

- オーケストレーション デザイナー  

- パイプライン デザイナー  

- BizTalk マッパー  

- BizTalk Server 管理コンソール  

### <a name="prerequisites"></a>前提条件  
 Microsoft をインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アクセスする前に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。  

### <a name="biztalk-server-tools"></a>BizTalk Server ツール  
 次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ドキュメントの一覧表示されているツールを使用する方法について説明します。  


|                                   ツール                                    |                                                                                                                                                                                              トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コア ドキュメント                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | -   [Visual Studio を使用](../../core/using-visual-studio.md) <br />-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)<br />-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> 詳細についての Visual Studio のソリューション、プロジェクト、およびにある項目について説明します[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)します。 |
|                          オーケストレーション デザイナー                           |                                                                                                                                                                                          [オーケストレーション デザイナーを使用してオーケストレーションの作成](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             パイプライン デザイナー                             |                                                                                                                                                                                                    [パイプライン デザイナーを使用してパイプラインを作成します。](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              BizTalk マッパー                               |                                                                                                                                                                                                            [BizTalk マッパーを使用してマップを作成します。](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   BizTalk Server 管理コンソール                   |                                                                                                                                                                                               [BizTalk Server 管理コンソールを使用します。](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a>Next
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)
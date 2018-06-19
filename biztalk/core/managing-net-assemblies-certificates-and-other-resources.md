---
title: .NET アセンブリ、証明書、およびその他のリソースの管理 |Microsoft ドキュメント
description: バインド ファイル、証明書、アセンブリ、仮想ディレクトリ、ファイル、および BizTalk Server の詳細を追加するリンク
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb74762bdf08e6e9e2a79650a26dedb0915ea8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262730"
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a>.NET アセンブリ、証明書、およびその他のリソースを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールと BTSTask コマンド ライン ツールを使用して、BizTalk アプリケーションの次の種類のリソース アイテムを管理する方法について説明します。 これらのリソース アイテムは、Visual Studio から BizTalk アプリケーションに自動的に展開できないため、手動でアプリケーションに追加する必要があります。 ただし、アプリケーションに追加した後は、アプリケーションおよびその他のアイテムで 1 つの単位としてインポート、エクスポート、およびインストールできます。  
  
-   **ファイル。** Readme ファイルなどのアドホック ファイルを含めることができます。 アプリケーションをインストールすると、ファイルはインストール フォルダーにコピーされます。  
  
-   **証明書。** BizTalk アプリケーションに証明書を追加することで、アプリケーションでパッケージ化して、証明書を BizTalk グループの 1 つから別のグループに送信することができるようになります。 証明書を送信ポートと受信場所に割り当てることにより、ID を検証し、安全なリンクを確立することができます。  
  
-   **COM と COM + コンポーネント。** マネージ COM コンポーネントとマネージ COM+ コンポーネントを含めることにより、BizTalk アプリケーションに追加機能を提供できます。  
  
-   **.NET アセンブリです。** 厳密には BizTalk アセンブリでない .NET アセンブリを BizTalk アプリケーションに含めることができます (BizTalk アセンブリは、BizTalk のオーケストレーション、パイプライン、スキーマ、またはマップを含む .NET アセンブリです)。  
  
-   **BAM 定義ファイル。** BAM を簡単に展開するには、BizTalk アプリケーションを作成し、これに BAM 定義を追加します。 その後、BizTalk アプリケーションの展開機能を使用すると、BAM 定義をさまざまな環境に展開できます。  
  
-   **バインド ファイルです。** バインド ファイルをアプリケーションに追加すると、アプリケーションをある展開環境から別の環境に迅速かつ容易に移動できます。  
  
-   **仮想ディレクトリです。** 仮想ディレクトリをアプリケーションに追加すると、これらのディレクトリをアプリケーションと共に展開できます。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順
  
-   [アプリケーションにファイルを追加します。](../core/how-to-add-a-file-to-an-application.md)  
  
-   [証明書をアプリケーションに追加します。](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [アプリケーションに COM コンポーネントを追加します。](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [.NET アセンブリをアプリケーションに追加します。](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [アプリケーションに BAM アイテムを追加します。](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [バインド ファイルをアプリケーションに追加します。](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [仮想ディレクトリをアプリケーションに追加します。](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更します。](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除します。](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)
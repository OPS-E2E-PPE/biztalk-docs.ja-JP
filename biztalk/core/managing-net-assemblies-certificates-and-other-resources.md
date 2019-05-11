---
title: .NET アセンブリ、証明書、およびその他のリソースの管理 |Microsoft Docs
description: バインド ファイル、証明書、アセンブリ、仮想ディレクトリ、ファイル、および BizTalk Server では、複数の追加へのリンク
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
ms.openlocfilehash: 9052b9a5bdee58e9d4cb3d51820905b492818fc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326596"
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a>.NET アセンブリ、証明書、およびその他のリソースを管理します。

## <a name="overview"></a>概要
このセクションでは、BizTalk Server 管理コンソールと BTSTask コマンド ライン ツールを使用して、次の種類のリソース アイテムを BizTalk アプリケーションを管理するについて説明します。 これらのリソース アイテムに自動的に展開できません、Visual Studio から BizTalk アプリケーションにため、アプリケーションに手動で追加する必要があります。 アプリケーションに追加される、ただし、することができますをインポート、エクスポート、およびこれらのアプリケーションとその他のアイテムのユニットとしてインストールします。  
  
-   **ファイル。** Readme ファイルなどのアドホック ファイルを含めることができます。 アプリケーションをインストールするときに、ファイルは、インストール フォルダーにコピーされます。  
  
-   **証明書。** 1 つの BizTalk グループから、別のアプリケーションをパッケージ化する証明書を転送できるようにアプリケーションに証明書ファイルを追加できます。 送信ポートおよび受信場所の id を確認して、セキュリティで保護されたリンクを確立するために証明書を割り当てます。  
  
-   **COM と COM + コンポーネント。** マネージ COM コンポーネントと、BizTalk アプリケーションに追加の機能を提供するマネージ COM + コンポーネントを含めることができます。  
  
-   **.NET アセンブリです。** 具体的には BizTalk アセンブリを BizTalk アプリケーション内ではない .NET アセンブリを含めることができます。 (BizTalk アセンブリは、BizTalk オーケストレーション、パイプライン、スキーマ、またはマップを含む .NET アセンブリです)。  
  
-   **BAM 定義ファイル。** BAM の展開を容易にするには、BizTalk アプリケーションを作成し、BAM 定義を追加しています。 さまざまな環境に BAM 定義を展開するのに BizTalk アプリケーションの展開機能を使用できます。  
  
-   **バインド ファイルです。** バインド ファイルを追加するには、アプリケーションを 1 つの展開環境から別のアプリケーションの移行も迅速かつ容易にします。  
  
-   **仮想ディレクトリ。** アプリケーションに仮想ディレクトリを追加するには、システムは、アプリケーションをデプロイできるようにします。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="next-steps"></a>次のステップ
  
-   [アプリケーションにファイルを追加する](../core/how-to-add-a-file-to-an-application.md)  
  
-   [証明書をアプリケーションに追加する](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [COM コンポーネントをアプリケーションに追加する](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [.NET アセンブリをアプリケーションに追加する](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [アプリケーションに BAM アイテムを追加する](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [アプリケーションにバインド ファイルを追加する](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [仮想ディレクトリをアプリケーションに追加する](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更します。](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [.NET アセンブリ、証明書またはその他のリソース アイテムをアプリケーションから削除する](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)
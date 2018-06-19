---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: true
ROBOTS: NOINDEX
title: 自動展開用の JSON テンプレートの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 0b7755a6-5a5a-4a6b-8f99-ac12a5fbf3d4
caps.latest.revision: 4
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 10d85b625d759af675ecc1a38d540da8a304ba43
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054522"
---
# <a name="configure-the-json-template-for-automatic-deployment"></a>自動展開用の JSON テンプレートを構成します。


Visual Studio Team Services を使用してアプリケーションをビルドすると、新しい BizTalk プロジェクト ファイルが作成 – (.btaproj)。 この新しいプロジェクトでは、VSTS を使用してビルドするすべての BizTalk アプリケーションを保持します。 

プロジェクトに含まれる、`BizTalkServerInventory.json`ファイル。 このファイルで、BizTalk アセンブリを追加、BizTalk アプリケーションのバインド ファイルを追加して配置シーケンスを設定します。 

このトピックでは、json ファイルを更新する方法を示します。 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a>アセンブリ、バインド ファイル、および配置シーケンスを追加します。

1. 開く、`BizTalkServerInventory.json`ファイルで、 **BizTalk Server アプリケーション**プロジェクト (.btaproj)。

2. テンプレートには、次のセクションが含まれています。 

    | | |
    |---|---|
    |BizTalkAssemblies | アプリケーションで使用するアセンブリ |
    |BindingFiles | バインド ファイルを参照しています|
    | DeploymentSequence | インストールする要素の順序|
    
    テンプレートのサンプル: 
    
    ![FP1 Json テンプレート イメージ 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > 複雑さによっては、ソリューションのこの JSON テンプレート ファイルでビルドに必要な要素を参照する必要があります。

3. `BizTalkAssemblies`、BizTalk アプリケーションで使用するアセンブリを追加します。 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. `BindingsFiles`、BizTalk アプリケーションのバインド ファイルを追加します。 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. `DeploymentSequence`、アプリケーション名を展開しをインストールし順序で追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. **保存**変更します。 

完了すると、Visual Studio チームのサービスの展開タスクは、必要なファイルと、インストールの順序は使用されます。 

## <a name="next-step"></a>次の手順
[トークンと変数を構成する](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)倍数に同じ BizTalk アプリケーションを展開する、バインド ファイルに[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s。

 
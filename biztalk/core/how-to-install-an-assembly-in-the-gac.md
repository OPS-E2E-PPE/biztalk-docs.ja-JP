---
title: アセンブリを GAC にインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e843d74b5420f8973f9d3663cfd05210c26996
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752367"
---
# <a name="how-to-install-an-assembly-in-the-gac"></a>GAC にアセンブリをインストールする方法
手動でインストールしてに付属する Gacutil ツールを使用してグローバル アセンブリ キャッシュ (GAC) 内の BizTalk アセンブリをアンインストール[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
 使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、BizTalk アセンブリがから配置されている場合、GAC に自動的にインストールすることが[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 このオプションで、BizTalk プロジェクトの展開のプロパティ設定します。参照してください[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)します。 このメソッドを使用して、BizTalk 以外の .NET アセンブリを GAC; にインストールすることはできませんこのトピックの説明に従って、手動でインストールする必要があります。  
  
> [!NOTE]
>  アセンブリを BizTalk アプリケーションに展開した後も、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアセンブリの展開オプションを指定できます。 参照してください[BizTalk アセンブリの展開オプションを変更する方法](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)、および[.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)します。  
  
## <a name="prerequisites"></a>前提条件  
GAC への書き込み権限を持つアカウントでサインインします。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  

  
## <a name="install-using-gacutil"></a>Gacutil を使用してインストールします。
  
1.  ローカル コンピューターに BizTalk アセンブリをコピーします。  
  
2.  開いている**Visual Studio 用開発者コマンド プロンプト**管理者として。  
  
3.  次のように入力します。  
  
     `gacutil /i path_to_assembly_file /f`

    たとえば、次のように入力します。  
    `gacutil /i c:\temp\filename.dll /f`
    
`/f`オプションには、同じアセンブリ名を持つ既存のアセンブリが上書きされます。 Gacutil コマンドおよびオプションの詳細については、次のように入力します。`gacutil /?`します。 

## <a name="uninstall-using-gacutil"></a>Gacutil を使用したアンインストールします。
グローバル アセンブリ キャッシュからアセンブリをアンインストールする (GAC) が完全にアプリケーションを展開解除する必要があります。 このプロセスを自動化することができます。 運用環境にアプリケーションを展開する前に、アプリケーションのアンインストール時に GAC からアセンブリを自動的にアンインストールする処理前のスクリプトを記述します。 参照してください[前処理および後処理のスクリプト アプリケーション展開のカスタマイズを使用した](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。  
  
 追加のファイルおよび設定を削除するのにスクリプトを使用することもできます。 参照してください[他のファイルと BizTalk アプリケーションの設定を削除する方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)します。  
 
#### <a name="using-the-windows-interface"></a>Windows インターフェイスを使用する場合  
  
1.  Systemdrive%\Windows\Assembly に開きます。  
  
2.  アプリケーションに含まれる各アセンブリ ファイルを右クリックして**アンインストール**、し、**はい**を確認します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  開いている**Visual Studio 用開発者コマンド プロンプト**管理者として。 
  
2.  次のように入力します。  
  
     `gacutil /u` \<*完全修飾アセンブリ名*\>  
  
     たとえば、次のように入力します。  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)   
 [BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)   
 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 

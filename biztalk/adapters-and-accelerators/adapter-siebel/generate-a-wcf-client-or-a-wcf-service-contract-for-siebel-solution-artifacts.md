---
title: WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, generate a client class by using svcutil.exe
- creating a proxy
- how to, create a proxy
- WCF service model, creating a proxy
- how to, generate a client class by using the Add Adapter Service Reference Plug-in
- how to, generate a client class
ms.assetid: 52c32c86-6403-4bb4-9d43-1319d19a6b49
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09cbd6fa8be325a31a6c3acd7ffb3c84092f9d63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010907"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts"></a>WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスを生成する Siebel の成果物を選択した操作を対象としました。 WCF クライアント クラスを生成するのに、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用することもできます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスから ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールを使用できない参照および検索の機能を提供し、Siebel システムに接続するときに選択したバインドのプロパティに基づいて構成ファイルを生成します。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF クライアント クラスの生成、プラグインのアダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio で Siebel 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)Siebel システムへの接続を検索および参照するには操作です。 選択した操作のための WCF クライアント クラスを作成することを確認します**クライアント (送信操作)** からが選択されている、**コントラクト型を選択します**(これは、既定値) のドロップダウン リスト。  
  
3. すべてのターゲット をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をプロジェクトに 2 つのファイルを追加します。  
  
- WCF クライアント コード ファイル。 このファイルには、生成された WCF クライアント クラスとヘルパーのコード選択した操作にはが含まれています。 初めて実行する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]既定の名前には、このファイルを生成、 **SiebelBindingClient.cs**します。 もう一度実行する場合は、次のファイルが生成されますが呼び出されます**SiebelBindingClient1.cs**します。  数値のサフィックスを生成する新しいファイルごとに 1 ずつ増加します。  既定のプレフィックスを変更することもできます**SiebelBinding**で別のプレフィックスを入力して、**ファイル名のプレフィックス**のフィールド、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]選択する前に**OK**に。ファイルを生成します。  
  
- **App.config**します。このファイルには、バインド構成との接続を構成したときに選択した内容に基づいてクライアント エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 App.config ファイルの内容に関する詳細については、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Svcutil.exe を使用して WCF クライアント クラスを生成します。  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスを生成することができます。 Svcutil.exe を使用すればを構成する必要があります、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。 構成と使用を svcutil.exe の詳細については、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[ServiceModel メタデータ ユーティリティ ツールを BizTalk adapter 用 Siebel eBusiness Applications を使用して](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)します。  
  
 Svcutil.exe は、output.cs の既定のファイル名を持つ出力ファイルで、WCF クライアント クラスを生成します。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)
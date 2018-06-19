---
title: WCF クライアントまたは Siebel ソリューションの成果物のための WCF サービス コントラクトを生成 |Microsoft ドキュメント
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
ms.openlocfilehash: c75615f0e6a3f6e4c947a7c13888558b7a666e77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222410"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts"></a>WCF クライアントまたは Siebel ソリューションの成果物のための WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Siebel の成果物に選択した操作を対象とした WCF クライアント クラスを生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスを生成します。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスを通じて ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 また、svcutil.exe ツールではない参照および検索機能を提供し、Siebel システムに接続するときに選択したバインドのプロパティに基づく構成ファイルが生成されます。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF クライアント クラスを生成する、プラグイン アダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Siebel 操作の Visual Studio でのメタデータを取得する](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)Siebel システムへの接続を検索および参照するには操作です。 選択した操作のための WCF クライアント クラスを作成することを確認**クライアント (送信操作)** からが選択されている、**選択コントラクト型**(これは、既定値) ドロップダウン リスト。  
  
3.  すべての対象をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 2 つのファイルをプロジェクトに追加します。  
  
-   WCF クライアント コード ファイル。 このファイルには、生成された WCF クライアント クラスとヘルパー コード選択した操作にはが含まれています。 初めて実行するとき、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]という既定の名前には、このファイルを生成、 **SiebelBindingClient.cs**です。 もう一度実行する場合、次のファイルが生成されますが呼び出されます**SiebelBindingClient1.cs**です。  数値のサフィックスが新しいファイルを生成するごとに 1 ずつ増加します。  既定のプレフィックスを変更することもできます**SiebelBinding**で別のプレフィックスを入力して、**ファイル名のプレフィックス**のフィールド、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]選択する前に**OK**に。ファイルを生成します。  
  
-   **App.config**です。このファイルには、バインド構成との接続を構成したときに選んだ内容に基づくクライアント エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 App.config ファイルの内容に関する詳細については、次を参照してください。 [Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>Svcutil.exe を使用して、WCF クライアント クラスを生成します。  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスを生成することができます。 と共に使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。 構成およびで svcutil.exe を使用の詳細については、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)です。  
  
 Svcutil.exe は、output.cs の既定のファイル名の出力ファイルで、WCF クライアント クラスを生成します。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)
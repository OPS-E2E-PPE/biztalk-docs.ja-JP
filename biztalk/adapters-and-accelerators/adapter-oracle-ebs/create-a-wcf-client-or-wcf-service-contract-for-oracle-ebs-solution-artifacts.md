---
title: WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ffd857-a177-423a-ae83-685d11b7aec6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9824e99014431c452f49d4a80e45efe4852c519f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986899"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-e-business-suite-solution-artifacts"></a>WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは Oracle E-business Suite の成果物を選択した操作を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラスを生成または WCF サービス コントラクトを使用することもできます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスから ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールを使用できない参照と検索の機能も提供し、Oracle E-business Suite に接続するときに選択したバインドのプロパティに基づいて構成ファイルを生成します。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>クライアント クラスの生成を使用して、プラグインのアダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)Oracle E-business Suite に接続して参照し、操作を検索します。 選択した操作のための WCF クライアント クラスを作成することを確認します**クライアント (送信操作)** からが選択されている、**コントラクト型を選択します**(これは、既定値) のドロップダウン リスト。  
  
3. すべてのターゲット をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をプロジェクトに 2 つのファイルを追加します。  
  
- **OracleEBSBindingClient.cs**します。 このファイルには、生成された WCF クライアント クラスとヘルパーのコード選択した操作にはが含まれています。  
  
- **App.config**します。このファイルには、バインド構成とクライアント エンドポイント構成が含まれています。 これらの構成はバインドとの接続を構成したときに選択した内容に基づいて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグインのアダプター サービス参照の追加  
 アダプターは、アダプターのクライアントにメッセージを送信する、Oracle E-business Suite を有効にする受信操作を公開します。 などの操作には、WCF サービス コントラクトを生成する必要があります。 このセクションでは、アダプターによって公開されている受信操作のサービス コントラクトを生成する方法について説明します。  
  
 使用して WCF サービス コントラクトを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>受信操作の WCF サービス コントラクトを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)Oracle E-business Suite に接続します。 いくつかのバインドのプロパティと、Oracle E-business Suite に接続するときに設定する URI プロパティがあります。  
  
3. Oracle E-business Suite に接続すると、選択**サービス (受信操作)** から、**選択コントラクト型**ドロップダウン リスト。  
  
4. **カテゴリを選択**ボックスに、サービス コントラクトを生成する受信操作を参照します。 たとえば、**通知**操作、ルート ノードをクリックします (**/**) を選択します**通知**から、**利用可能なカテゴリと操作**ボックスをクリックして**追加**します。 受信操作を参照する方法の詳細については、次を参照してください。[参照、検索、および Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  
  
5. 操作の WCF サービス コントラクトを生成する をクリックして**OK**します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
- **OracleEBSBindingInterface.cs**します。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と受信操作のヘルパー コード。  
  
- **OracleEBSBindingService.cs**します。 このファイルには、OracleDBBindingInterface.cs で定義されているインターフェイスを実装するクラスが含まれています。 受信操作によって返されるレコードを処理するビジネス ロジックを実装することができます。  
  
- **App.config**します。このファイルには、バインド構成、エンドポイントの動作、およびバインドとの接続を構成したときに選択した内容に基づくサービス エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Svcutil.exe を使用して WCF クライアント クラスまたは WCF サービス コントラクトを生成するには  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスまたは WCF サービスのインターフェイスを生成することができます。 Svcutil.exe を使用すればを構成する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
 Svcutil.exe は、出力ファイルで、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。 既定のファイル名は、output.cs です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。 Svcutil.exe の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=139432](http://go.microsoft.com/fwlink/?LinkId=139432)します。
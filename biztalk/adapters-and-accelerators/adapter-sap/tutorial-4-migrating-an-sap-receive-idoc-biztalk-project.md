---
title: "チュートリアル 4: SAP を移行する BizTalk プロジェクトの IDOC を受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943c80e84bc192330fd870a45c0b5fb60761a33d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a>チュートリアル 4: SAP を移行する BizTalk プロジェクトの IDOC を受信
Microsoft BizTalk Server に付属している SAP アダプターの以前のバージョンが WCF ベース異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。  
  
-   デザイン時に、BizTalk プロジェクトを作成する操作。  
  
-   メタデータの取得エクスペリエンス。  
  
-   スキーマ ファイル名と名前空間。  
  
-   データは、マッピングを入力します。  
  
-   アダプターを使用して実行できる操作です。  
  
-   BizTalk Server 管理コンソールで物理ポートの構成。  
  
 これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの SAP アダプター](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)です。  
  
 ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
 このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。  
  
> [!NOTE]
>  ここでは簡略化のため、このチュートリアルでは、SAP アダプターの以前のバージョンを vPrev SAP アダプターと呼びます。 同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。  
  
## <a name="sample-used-for-the-tutorial"></a>チュートリアルでは、使用されるサンプル  
 このチュートリアルは、SAP システムからフラット ファイル IDOC を受信する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (ReceiveIDOC_Migration) に基づいています。 サンプルが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、SAP システムから ORDERS03 IDOC を受信する BizTalk プロジェクトが含まれます。  
  
-   [厳密な名前キー ファイルを作成し、ツールの説明](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 IDOC を受信する vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**です。 これは、単純な SAP で構成されるオーケストレーションの受信フラット ファイル IDOC を SAP システムから受信するポート。 BizTalk プロジェクトには、オーケストレーションで使用できるように、フラット ファイル IDOC を XML に変換する、フラット ファイル逆アセンブラーが含まれています。 で XML IDOC を file ポートを介してファイルの場所にコピーすると、前に、フラット ファイル アセンブラーを使用してフラット ファイル IDOC に変換されます。  
  
-   **SAP システムに送信する IDOC のスキーマ**です。 このチュートリアルには、SAP システムから ORDERS03 IDOC を受信する BizTalk プロジェクトが含まれます。 IDOC に対して生成されたスキーマは、ORDERS03.xsd です。 このスキーマは、vPrev SAP アダプターを使用して生成されます。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行チュートリアルの目的は、vPrev SAP アダプターの送信ポートではなく Wcf-custom 送信ポートを使用して SAP システムからフラット ファイル IDOC を受信するためです。 どのような設定が必要、Wcf-custom 送信ポートの詳細については、前に、まず vPrev 送信 IDOC オーケストレーションに必要などのような物理ポートを理解する必要があります。  
  
-   VPrev SAP では、SAP システムからフラット ファイル IDOC を受信するポートを受信します。 ポートもこれに変換が使用可能なフラット ファイル逆アセンブラーを使用して XML IDOC vPrev BizTalk アプリケーションの一部として。 XML IDOC スキーマに準拠する (ORDERS03.xsd) vPrev SAP アダプターを使用して生成されることです。  
  
-   IDOC をフォルダーにコピーする file 送信ポート。 また、このポートは、XML IDOC をフラット ファイル IDOC に変換するのに BizTalk アプリケーションで使用可能なフラット ファイル アセンブラー パイプラインを使用します。  
  
 既存 vPrev BizTalk プロジェクトを移行するには、フラット ファイル IDOC をフォルダーにコピーする file 送信ポートを変更する必要はありません。 新しいを構成するだけ済みます Wcf-custom 受信ポートを右の構成設定を使用します。 このチュートリアルは、Wcf-custom を構成する方法を示します WCF ベースを使用して SAP システムから Idoc を受信する受信ポート[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: 構築して、IDOC を受信するため vPrev BizTalk プロジェクトを配置](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [手順 2: 構成 Wcf-custom 一方向受信ポート](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [手順 3: 移行後のアプリケーションをテストします。](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)
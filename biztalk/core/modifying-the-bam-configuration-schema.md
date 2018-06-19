---
title: BAM 構成スキーマの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuration schema [BAM]
- managing [BAM], configuration schema
- BAMConfiguration.xml file
ms.assetid: 8901fb05-1519-4033-8489-67a9b745ed43
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87721445a19cff96799418c019560d09a1287488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263282"
---
# <a name="modifying-the-bam-configuration-schema"></a><span data-ttu-id="a3580-102">BAM 構成スキーマの変更</span><span class="sxs-lookup"><span data-stu-id="a3580-102">Modifying the BAM Configuration Schema</span></span>
<span data-ttu-id="a3580-103">この構成ファイルは、構成ウィザードで自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3580-103">The Configuration Wizard creates this configuration file automatically.</span></span> <span data-ttu-id="a3580-104">サーバー名または他の構成情報を変更する場合、展開の完了後に、このファイルを手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3580-104">You must modify this file manually if you change your server names or other configuration information after you complete the deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3580-105">BAM 構成ファイルに加えた変更を反映するには、管理者が、現在展開している BAM 構成の展開を解除し、更新した BAMConfiguration.xml を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3580-105">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="a3580-106">BAM 定義を展開解除については、次を参照してください。 [BAM 定義を展開解除](../core/how-to-remove-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="a3580-106">For information about undeploying a BAM definition, see [Undeploying BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="a3580-107">BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義の展開](../core/how-to-deploy-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="a3580-107">For information about deploying a BAM definition, see [Deploying BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="a3580-108">BAMConfiguration.xml ファイルに使用されているスキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3580-108">The following is the schema used for the BAMConfiguration.xml file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="urn:schemas-microsoft.com:BAM" targetNamespace="urn:schemas-microsoft.com:BAM" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
     <xs:element name="BAMConfiguration">  
          <xs:complexType>  
               <xs:sequence>  
                    <xs:element name="DeploymentUnit" maxOccurs="unbounded" type="DeploymentUnit" />  
               </xs:sequence>  
          </xs:complexType>  
     </xs:element>  
     <xs:complexType name="DeploymentUnit">  
          <xs:sequence>  
               <xs:element name="Property" maxOccurs="unbounded" type="Property" />  
          </xs:sequence>  
          <xs:attribute name="Name" type="xs:string" />  
     </xs:complexType>  
     <xs:complexType name="Property">  
          <xs:simpleContent>  
               <xs:extension base='xs:string'>  
                    <xs:attribute name='Name' type='xs:NCName' />  
               </xs:extension>  
          </xs:simpleContent>  
     </xs:complexType>  
</xs:schema>  
```  
  
 <span data-ttu-id="a3580-109">BAM 構成スキーマに準拠した XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3580-109">The following example is an XML file that conforms to the BAM configuration schema.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<BAM:BAMConfiguration xmlns:BAM='urn:schemas-microsoft.com:BAM' xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance'>  
     <DeploymentUnit Name="PrimaryImportDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMPrimaryImport</Property>  
          <Property Name="RTAWindow">60</Property>  
          <Property Name="RTATimeSlice">5</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="StarSchemaDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMStarSchema</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="AnalysisDatabase">  
          <Property Name="ServerName">localhost</Property>  
          <Property Name="DatabaseName">BAMAnalysis</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="ArchivingDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMArchiving</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="CubeUpdateDTS">  
          <Property Name="ConnectionTimeOut">15</Property>  
          <Property Name="UseEncryption">1</Property>  
          <Property Name="OwnerPassword">myOwnerPassword</Property>  
          <Property Name="UserPassword">myUserPassword</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="DataMaintenanceDTS">  
          <Property Name="ConnectionTimeOut">15</Property>  
          <Property Name="UseEncryption">1</Property>  
          <Property Name="OwnerPassword">myOwnerPassword</Property>  
          <Property Name="UserPassword">myUserPassword</Property>       
     </DeploymentUnit>  
</BAM:BAMConfiguration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3580-110">参照</span><span class="sxs-lookup"><span data-stu-id="a3580-110">See Also</span></span>  
 <span data-ttu-id="a3580-111">[BAM 構成スキーマ](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="a3580-111">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="a3580-112">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="a3580-112">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="a3580-113">ビジネス アクティビティ監視 (BAM)</span><span class="sxs-lookup"><span data-stu-id="a3580-113">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)
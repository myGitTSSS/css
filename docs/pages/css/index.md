import {Box, Flex, Heading, Link, Text} from '@primer/components'
import {
  MetaPackageBox,
  PrimerPackageBox,
  PrimitivesOverview,
  StylesOverview
} from '../../src/landing'
import {CONTENT_MAX_WIDTH} from '../../src/constants'
import {name, version} from 'primer/package.json'
import packages from './packages.json'

# Introduction

Our goal is to create a system that enables us to build consistent user experiences with ease, yet with enough flexibility to support the broad spectrum of GitHub websites. This goal is embedded in our design and code decisions. Our approach to CSS is influenced by Object Oriented CSS principles, functional CSS, and BEM architecture.

## Highly reusable, flexible styles

Styles can be mixed and matched to achieve many different layouts, independent of their location. These styles fall into three categories:

<StylesOverview m={6} />

## Systematically designed for GitHub

Primer is built upon systems that form the foundation of our styles such as spacing, typography, and color. This systematic approach helps ensure our styles are consistent and interoperable with each other.

<PrimitivesOverview />

## Primer packages

Each component or group of styles is packaged up and distributed via npm. Primer includes 23 packages that are grouped into useful meta-packages for easy install. Each package and meta-package is independently versioned and distributed via npm, so it's easy to include all or part of Primer within your own project.

<PrimerPackageBox data={packages.primer} count={Object.keys(packages).length - 1} mb={4} />

<Flex justifyContent="space-around" mb={6}>
  <MetaPackageBox title="Core" data={packages['primer-core']} width={1/3}>
    The core package contains modules that are shared between GitHub product and marketing websites.
  </MetaPackageBox>
  <MetaPackageBox title="Product" data={packages['primer-product']} width={1/3}>
    The product package contains modules that are used on GitHub product websites.
  </MetaPackageBox>
  <MetaPackageBox title="Marketing" data={packages['primer-marketing']} width={1/3}>
    The marketing package contains modules that are used on GitHub marketing websites.
  </MetaPackageBox>
</Flex>


<div class="bg-gray py-6">
  <div class="d-flex flex-wrap flex-md-nowrap px-6 gutter-lg">
    <div class="col-12 col-md-9 pr-0 pr-lg-2">
      <h3 class="f3 text-normal m-0">Use Primer in your project</h3>
      <p class="my-3">Pick and choose what you need. Install the entire Primer bundle or individual packages via npm.</p>
      <a href="/css/getting-started/" class="btn btn-outline">Installation instructions</a>
    </div>
  </div>
</div>

export const Hero = () => (
  <Box bg="blue.5">
    <Box maxWidth={CONTENT_MAX_WIDTH} p={6} mx="auto" mb={3}>
      <Box mt={4} mb={4}>
        <Heading color="white" fontSize={7} fontWeight="light">
          Primer CSS
        </Heading>
        <Text is="div" color="blue.2" fontSize={2} fontFamily="mono" mb={4}>
          {name}@{version}
        </Text>
        <Text is="p" color="white" fontSize={4} fontWeight="light">
          Resources for building websites with{' '}
          <Link color="inherit" underline href="https://primer.style">
            Primer
          </Link>{' '}
          in CSS and Sass.
        </Text>
      </Box>
    </Box>
  </Box>
)